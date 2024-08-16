<template>
	<div ref="pickerView" class="ch-picker-view" @touchstart="touchstart" @touchmove.prevent="touchmove"
		@touchend="touchend">

		<div class="ch-picker-view__scroll" :style="{
			height: `${_itemHeight * visibleCount}px`,
			'--background': `linear-gradient(to bottom, #fff 0%, transparent ${_itemHeight*(_getMaskTopCount+0.4)}px, transparent ${_itemHeight*(_getMaskTopCount+1-0.4)}px,  #fff 100%)`,
		}">
			<div class="ch-picker-view__scroll-masktop" :style="{height:`${_itemHeight * _getMaskTopCount}px`}"></div>
			<div class="ch-picker-view__scroll-maskbottom" :style="{height:`${_itemHeight*_getMaskBottomCount}px`}"></div>

			<div class="ch-picker-view__scroll-box" :style="{
						marginTop:`${_itemHeight * _getMaskTopCount}px`,
						transform: `translateY(${translateY}px)`,
				}">
				<div class="ch-picker-view__scroll-box-item textHide-span" :style="[_itemStyle]" v-for="(item,index) in column"
					:key="index" @tap="handleColumn(item,index)">
					<template v-if="_fieldsMode==='default'">{{item}}</template>
					<template v-else-if="_fieldsMode==='json'">{{item[_fields.label]}}</template>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	const screenWidth = uni.getSystemInfoSync().screenWidth

	export default {
		props: {
			// 列数
			colCount: {
				type: Number,
				default: 0
			},
			// 列下标
			colIndex: {
				type: Number,
				default: 0
			},
			// 列数据
			column: {
				type: Array,
				default: () => []
			},
			// 默认值
			defaultIndex: {
				type: Number,
				default: 0
			},
			// value：数据值 label：数据名
			fields: {
				type: Object,
				default: () => {
					return {}
				}
			},
			// 单个选项的高度，会覆盖_itemStyle内的height；
			// 单位是px
			itemHeight: {
				type: [String, Number],
				default: 44
			},
			// 单个选项样式
			itemStyle: {
				type: Object,
				default: () => {}
			},
			// 每列中可见选项的数量，最大为5,最小为3
			visibleCount: {
				type: Number,
				default: 5
			},
		},
		data() {
			return {
				touchStartY: 0, // 触屏起始点y
				deltaY: 0, // 手指位移,
				translateY: 0, // box位移
				isTouching: false, // 正在滑动

				default: {
					fieldsValue: 'value',
					fieldsLabel: 'label',
				},
			}
		},
		computed: {
			_fields() {
				return {
					value: this.fields.value || this.default.fieldsValue,
					label: this.fields.label || this.default.fieldsLabel,
				}
			},
			// 格式: 默认default  数组json
			_fieldsMode() {
				if (this.column && this.column.length && typeof this.column[0] === 'object') {
					return 'json'
				} else {
					return 'default'
				}
			},
			// 实际单个选项的高度 主要是统一变量类型
			_itemHeight() {
				return typeof this.itemHeight === 'string' ? parseFloat(this.itemHeight) : this.itemHeight
			},
			// 实际单个选项的样式
			_itemStyle() {
				return {
					...this.itemStyle,
					height: `${this._itemHeight}px`,
					lineHeight: `${this._itemHeight}px`,
				}
			},
			// 实际滚动区域内容的高度
			_scrollInnerH() {
				return this._itemHeight * (this.column.length - 1)
			},
			_getMaskTopCount() {
				return Math.floor((this.visibleCount - 1) / 2)
			},
			_getMaskBottomCount() {
				return Math.ceil((this.visibleCount - 1) / 2)
			}
		},
		watch: {
			defaultIndex: {
				handler(nVal, oVal) {
					if (this.isTouching) {
						return
					}
					this.translateY = nVal * this._itemHeight * -1
				},
				immediate: true
			},
			translateY(nVal, oVal) {
				let tIndex = Math.floor(Math.abs(nVal) / this._itemHeight)
				tIndex = tIndex > this.column.length - 1 ? this.column.length - 1 : tIndex
				this.$emit('change', tIndex)
			},
		},
		mounted() {
			// #ifdef H5
			// 监听鼠标滚轮
			this.$refs.pickerView.addEventListener('mousewheel', this.mouseHandle, false)
			// #endif
		},
		methods: {
			// 鼠标滚轮触发 - start
			mouseHandle(e) {
				let clientX = e.clientX
				let rangeWidth1 = screenWidth / this.colCount * (this.colIndex)
				let rangeWidth2 = screenWidth / this.colCount * (this.colIndex + 1)
				if (clientX < rangeWidth1 || clientX >= rangeWidth2) {
					return
				}

				if (e.target.className === 'ch-picker-mask') {
					return
				}

				let tTranslateY = this.translateY
				if (e.deltaY > 0) {
					// console.log('向下');
					tTranslateY -= this._itemHeight
					tTranslateY = tTranslateY < this._scrollInnerH * -1 ? this._scrollInnerH * -1 : tTranslateY
				} else {
					// console.log('向上');
					tTranslateY += this._itemHeight
					tTranslateY = tTranslateY > 0 ? 0 : tTranslateY
				}
				this.translateY = tTranslateY
			},
			// 鼠标滚轮触发 - end

			// 触摸触发 - start
			touchstart(e) {
				this.isTouching = true

				let tTouche = e.touches[0]
				// console.log('touchstart', tTouche.clientY);
				this.touchStartY = tTouche.clientY
				this.deltaY = 0
			},
			touchmove(e) {
				this.isTouching = true

				let tTouche = e.touches[0]
				// console.log('touchmove', tTouche.clientY);
				let preDeltaY = this.deltaY
				this.deltaY = tTouche.clientY - this.touchStartY
				let tDiff = this.deltaY - preDeltaY
				this.translateY += tDiff
			},
			touchend(e) {
				// console.log('touchend');
				this.isTouching = false

				let tTranslateY = 0
				let divisor = this.translateY / this._itemHeight

				divisor = this.deltaY > 0 ? Math.ceil(divisor) : Math.floor(divisor)
				tTranslateY = divisor * this._itemHeight
				tTranslateY = tTranslateY > 0 ? 0 : tTranslateY
				tTranslateY = tTranslateY < this._scrollInnerH * -1 ? this._scrollInnerH * -1 : tTranslateY
				// console.log(tTranslateY);
				this.translateY = tTranslateY
			},
			// 触摸触发 - end
			handleColumn(item, index) {
				this.translateY += (this.defaultIndex - index) * this._itemHeight
			}
		}
	}
</script>
<style lang="scss" scoped>
	.ch-picker-view {
		display: flex;
		align-items: center;

		.ch-picker-view__scroll {
			position: relative;
			width: 100%;
			overflow: hidden;
			z-index: 1;

			&::before {
				content: "";
				position: absolute;
				inset: 0;
				background: var(--background);
				pointer-events: none;
				z-index: 99;
			}

			.ch-picker-view__scroll-masktop,
			.ch-picker-view__scroll-maskbottom {
				position: absolute;
				width: 100%;
				z-index: 1;
				border: 0 solid transparent;
				border-image: linear-gradient(to right, transparent, #ddd, transparent) 1;
				pointer-events: none;
				z-index: 101;
			}

			.ch-picker-view__scroll-masktop {
				top: 0;
				border-bottom-width: 1px;
			}

			.ch-picker-view__scroll-maskbottom {
				bottom: 0;
				border-top-width: 1px;
			}

			.ch-picker-view__scroll-box {
				transition: all 200ms linear;

				.ch-picker-view__scroll-box-item {
					padding: 0 10rpx;
					text-align: center;
				}
			}
		}

		.textHide-span {
			overflow: hidden;
			text-overflow: ellipsis;
			word-break: break-all;
			white-space: nowrap;
		}
	}
</style>