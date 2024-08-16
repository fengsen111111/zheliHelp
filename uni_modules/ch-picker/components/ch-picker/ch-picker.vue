<template>
	<div v-show="visible" class="ch-picker">
		<div class="ch-picker__mask" :class="{'mask-show':maskVisible}" @tap.stop.prevent="maskHandle"></div>
		<div class="ch-picker__content" :class="[`ch-picker__content-${position}`,{'show':maskVisible}]"
			:style="{'--contentWidth':actWidth}">
			<!-- <div class="ch-picker__content-toolbar">
				<div @tap.stop.prevent="closeHandle">取消</div>
				<div @tap.stop.prevent="confirmHandle">确定</div>
			</div> -->
			<div class="flex justify-between text-center items-center mt30 px20">
				<div class="w28"></div>
				<div class="font-bold text34">
					选择类型
				</div>
				<div>
					<uni-icons type="closeempty" size="20" color="#666666" @tap.stop.prevent="closeHandle"></uni-icons>
				</div>
			</div>

			<div class="ch-picker__content-columns px20">
				<div class="ch-picker__content-column" :style="{'--col':columns.length}" v-for="(column,index) in columns"
					:key="index">
					<ch-picker-view :column="column" :itemHeight="itemHeight" :visibleCount="actVisibleCount"
						:itemStyle="itemStyle" :defaultIndex="defaultIndex[index]" :fields="fields" :colCount="columns.length"
						:colIndex="index" @change="(e)=>indexChange(index,e)">
					</ch-picker-view>
				</div>
			</div>
			
			<div class="flex justify-between text30 px20 mb20">
				<div class="text-center bg-white w320 py20 borderFA6C2F radius10 colFA6C2F" @tap.stop.prevent="closeHandle">取消</div>
				<div class="text-center w320 py20 bgFA6C2F radius10 col-white">确定</div>
			</div>
		</div>
	</div>
</template>

<script>
	function formatPropSize(size) {
		let tUnit = 'px'
		let result = ''
		if (typeof size === 'string') {
			result = parseFloat(size)
			tUnit = size.replace(result.toString(), '')
			result = `${result}${tUnit}`
		} else if (typeof size === 'number') {
			result = `${size}${tUnit}`
		}
		return result
	}

	export default {
		props: {
			// 点击遮罩层关闭
			clickMaskClose: {
				type: Boolean,
				default: true
			},
			// 每一列的数据
			columns: {
				type: Array,
				default: () => []
			},
			// 默认选中值的下标，是数组
			defaultIndex: {
				type: Array,
				default: () => []
			},
			// 悬浮位置 top/center/bottom
			position: {
				type: String,
				default: 'bottom'
			},
			// 每列中可见选项的数量，最大为5,最小为3
			visibleCount: {
				type: [String, Number],
				default: 5
			},
			// position为center时生效
			// 不含单位时，默认单位是px
			width: {
				type: [String, Number],
				default: '60vw'
			},


			// 子级使用 - start
			// 单个选项的高度，会覆盖itemStyle内的height；
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
			// 数组属性
			fields: {
				type: Object,
				default: () => {
					return {}
				}
			},
		},
		data() {
			return {
				visible: false,
				maskVisible: false,
				curIndexs: new Array(),
				visibleCountMax: 5, // 每列中最多可见选项的数量
				visibleCountMin: 3, // 每列中最少可见选项的数量
			}
		},
		computed: {
			// 实际面板的宽度
			actWidth() {
				return formatPropSize(this.width)
			},
			// 实际每列中可见选项的数量 主要是统一变量类型
			actVisibleCount() {
				let result = typeof this.visibleCount === 'string' ? parseFloat(this.visibleCount) : this.visibleCount
				result = result > this.visibleCountMax ? this.visibleCountMax : result
				result = result < this.visibleCountMin ? this.visibleCountMin : result
				return result
			},
		},
		watch: {
			defaultIndex: {
				handler(nVal, oVal) {
					if (typeof nVal !== 'object') {
						return
					}
					this.curIndexs = JSON.parse(JSON.stringify(nVal))
				},
				deep: true,
				immediate: true
			},
		},
		methods: {
			show() {
				this.visible = true
				setTimeout(() => {
					this.maskVisible = true
				}, 250)
			},
			hide() {
				this.maskVisible = false
				setTimeout(() => {
					this.visible = false
				}, 250)
			},
			maskHandle() {
				if (!this.clickMaskClose) {
					return
				}
				this.hide()
			},
			closeHandle() {
				this.$emit('cancel')
				this.hide()
			},
			confirmHandle() {
				let result = this.formatReturn()
				this.$emit('confirm', result)
				this.hide()
			},
			formatReturn() {
				let tIndexs = []
				let tColumns = []
				for (let i = 0; i < this.columns.length; i++) {
					let tIndex = this.curIndexs[i] || 0
					tIndexs.push(tIndex)
					tColumns.push(this.columns[i][tIndex])
				}
				return {
					indexs: tIndexs,
					columns: tColumns,
				}
			},
			indexChange(index, e) {
				// console.log(index, e);
				this.$set(this.curIndexs, index, e)

				let result = this.formatReturn()
				this.$emit('change', result)
			}
		}
	}
</script>
<style lang="scss" scoped>
	.ch-picker {
		color: initial;

		.ch-picker__mask {
			position: fixed;
			top: 0;
			right: 0;
			bottom: 0;
			left: 0;
			z-index: 1023;
			background-color: rgba(0, 0, 0, 0.5);

			opacity: 0;
			transition: all .5s;

			&.mask-show {
				opacity: 1;
			}
		}

		.ch-picker__content {
			position: fixed;
			background-color: #fff;
			border-radius: 20rpx;
			z-index: 1024;
			transition: all .5s;
			display: flex;
			flex-direction: column;

			.ch-picker__content-toolbar {
				height: 48px;
				padding: 0 15px;
				font-size: 13px;
				// background-color: #f8f8f8;

				display: flex;
				justify-content: space-between;
				align-items: center;

				>div:last-child {
					color: #0055ff;
				}
			}

			.ch-picker__content-columns {
				padding-bottom: calc(24rpx + constant(safe-area-inset-bottom));
				padding-bottom: calc(24rpx + env(safe-area-inset-bottom));


				display: flex;
				align-items: center;

				.ch-picker__content-column {
					width: calc(100% / var(--col));
					flex: 0 0 auto;
				}
			}
		}

		.ch-picker__content-top {
			top: 0;
			left: 0;
			width: 100vw;
			transform: translateY(-100%);
			flex-direction: column-reverse;

			&.show {
				transform: translateY(0);
			}
		}

		.ch-picker__content-center {
			top: 50%;
			left: 50%;
			width: var(--contentWidth);
			transform: translate(-50%, -50%) scale(0);

			&.show {
				transform: translate(-50%, -50%) scale(1);
			}
		}

		.ch-picker__content-bottom {
			bottom: 0;
			left: 0;
			width: 100vw;
			transform: translateY(100%);

			&.show {
				transform: translateY(0);
			}
		}

		::-webkit-scrollbar {
			display: none;
		}
	}
</style>