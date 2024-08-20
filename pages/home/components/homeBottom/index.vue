<template>
	<view class="">
		<view class="mt20">
			<view class="flex col999999 text-center">
				<view class="" :class="checkIndex==1?'col-black text32 font-bold':''" @click="handleIndex(1)">
					推荐商品
					<view class="checkItem mx-auto" v-if="checkIndex==1"></view>
				</view>
				<view class="ml100" :class="checkIndex==2?'col-black text32 font-bold':''" @click="handleIndex(2)">
					团购
					<view class="checkItem mx-auto" v-if="checkIndex==2"></view>
				</view>
				<view class="ml100" :class="checkIndex==3?'col-black text32 font-bold':''" @click="handleIndex(3)">
					组合套餐
					<view class="checkItem mx-auto" v-if="checkIndex==3"></view>
				</view>
			</view>
			<!-- 推荐商品 -->
			<view v-if="checkIndex==1">
				<view class="mt10 flex text24" styule="">
					<view class="tags" :class="item == 1?'col-black':'col999999'" v-for="item in [1,2,3,4,5]"
						:key="item">热门</view>
				</view>
				<view class="grid grid-cols-2">
					<shopItem v-for="item in [1,2,3,4]" :key="item" />
				</view>
			</view>
			<!-- 团购 -->
			<view v-else-if="checkIndex==2">
				<view class="flex justify-between mt20">
					<view class="bg-white flex items-center text20 radius8 py6 px10" @click="pickerShow">
						<text>{{columns[0][curIndexs[0]].label}}</text>
						<image src="@/static/home/time.png" class="w28 h28 ml10" mode=""></image>
					</view>
					<view class="bg-white flex items-center text20 radius8 py6 px10" @click="toggle('bottom')">
						<text>全部</text>
						<uni-icons type="down" color="#FA6C2F" class="ml10" size="16"></uni-icons>
					</view>
				</view>
				<view @click="handleGo" v-for="item in [1,2,3,4,5]" :key="item">
					<itemBuy />
				</view>
			</view>
			<!-- 组合套餐 -->
			<view v-else-if="checkIndex==3">
				<view class="grid grid-cols-2">
					<view class="" @click="handleCombo" v-for="item in [1,2,3,4]" :key="item" >
						<shopItem />
					</view>
				</view>
			</view>
		</view>
		<!-- 时间弹框 -->
		<view class="" @touchmove.stop.prevent="() => {}">
			<ch-picker ref="ChPicker" position="bottom" :columns="columns" :defaultIndex="curIndexs"
				@change="pickerChange"></ch-picker>
		</view>
		<!-- 全部筛选 -->
		<view>
			<uni-popup ref="popup" background-color="#fff"  borderRadius="20rpx 20rpx 0px 0px">
				<view class="radius20 bg-white p30" style="height: 30vh;">
					<view class="flex justify-between">
						<view class="w28"></view>
						<view class="">选择类型</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancel"></uni-icons>
						</view>
					</view>
					<!--  -->
					<view class="grid grid-cols-4 text30 text-center mt50">
						<view class="col-black mb30">全部</view>
						<view class="col999999 mb30">酒水饮料</view>
						<view class="col999999 mb30">日用百货</view>
						<view class="col999999 mb30">生鲜蔬菜</view>
						<view class="col999999 mb30">儿童玩具</view>
					</view>
					<!--  -->
					<div class="flex justify-between text30 px20 mt50 mb20">
						<div class="text-center bg-white w320 py20 borderFA6C2F radius10 colFA6C2F" @click="cancel">取消</div>
						<div class="text-center w320 py20 bgFA6C2F radius10 col-white">确定</div>
					</div>
				</view>
			</uni-popup>
		</view>

	</view>
</template>

<script>
	import shopItem from '../shopItem/index.vue'
	import itemBuy from '../itemBuy/index.vue'
	export default {
		components: {
			shopItem,
			itemBuy
		},
		data() {
			return {
				checkIndex: 2,
				curIndexs: [1],
				columns: [
					[{
							label: "11:00 - 12:00",
							value: 1,
						}, {
							label: "12:00 - 13:00",
							value: 2,
						}, {
							label: "13:00 - 14:00",
							value: 3,
						},
						{
							label: "14:00 - 15:00",
							value: 4,
						},
						{
							label: "15:00 - 16:00",
							value: 5,
						},
					],
				],
				// 
				type: 'center',
			}
		},
		methods: {
			handleIndex(index) {
				this.checkIndex = index
			},
			pickerShow() {
				this.$refs.ChPicker.show()
			},
			pickerChange(e) {
				// console.log(e);
				this.curIndexs = e.indexs
			},
			// 
			toggle(type) {
				this.type = type
				// open 方法传入参数 等同在 uni-popup 组件上绑定 type属性
				this.$refs.popup.open(type)
			},
			cancel(){
				this.$refs.popup.close()
			},
			// 团购详情
			handleGo(){
				uni.navigateTo({
					url: '/pages/childPages/buyDetails/index'
				})
			},
			// 组合详情
			handleCombo(){
				uni.navigateTo({
					url: '/pages/childPages/comboDetails/index'
				})
			},
		}
	}
</script>

<style>
	.tags {
		width: 300px;
		text-align: center;
	}
</style>