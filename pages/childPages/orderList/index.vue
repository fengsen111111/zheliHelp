<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="订单列表" color="#000000" @clickLeft="back" />
		</view>
		<view class="bgF4F6F5 p30">
			<view class="flex px30 justify-between text-center ">
				<view @click="handleIndex(1)" :class="checkIndex==1?'text32 col333333':'text28 col999999'">待付款<view class="checkItem mx-auto mt5" v-if="checkIndex==1"></view></view>
				<view @click="handleIndex(2)" :class="checkIndex==2?'text32 col333333':'text28 col999999'">待发货<view class="checkItem mx-auto mt5" v-if="checkIndex==2"></view></view>
				<view @click="handleIndex(3)" :class="checkIndex==3?'text32 col333333':'text28 col999999'">待收货<view class="checkItem mx-auto mt5" v-if="checkIndex==3"></view></view>
				<view @click="handleIndex(4)" :class="checkIndex==4?'text32 col333333':'text28 col999999'">售后<view class="checkItem mx-auto mt5" v-if="checkIndex==4"></view></view>
			</view>
			<!--  -->
			<view class="bg-white radius10  mt20" v-for=" item in [1,2,3] " :key="item">
				<view class="flex text24  justify-between p20">
					<view class="font-bold">订单编号:123456789</view>
					<view class="font-bold col36A9FC">商品</view>
				</view>
				<view class="bg999999 h1 my10"></view>
				<view class="flex text24  justify-between p20">
					<view class="">下单时间:2024-06-26</view>
					<view class="text20 col36A9FC">快递单号 XXXXXXXXXXXXXXX</view>
				</view>
				<view class="bg999999 h1 my10"></view>
				<view class="flex text24  justify-between p20">
					<view class="font-bold">商品信息</view>
					<view class="text20 colFA6C2F" v-if="status" @click="handleStatsu">展开</view>
					<view class="text20 colFA6C2F" v-else @click="handleStatsu">收起</view>
				</view>
				<view class="" v-if="status">
					<view class="p20 flex justify-between items-center" v-for="item in [1,2,3]" :key="item">
						<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="h100 w100 radius10"
							mode=""></image>
						<view class="ml20">
							<view class="text24 font-bold">陈昌银重庆磁器口精品豪华陈麻花百草味藕片零食</view>
							<view class="col999999 text24">袋装(500g)</view>
						</view>
						<view class="text30 ml20">
							X666
						</view>
					</view>
				</view>
				<view class="p20 flex items-center justify-between">
					<view class="text24 col666666">实付金额：</view>
					<view class="flex items-center">
						<view class="col666666 text20">运费</view>
						<view class="colFF0000 text20 ml10">+￥66</view>
						<view class="font-bold colFF0000 text34 ml40">￥100</view>
						<view v-if="checkIndex==1" class="col-white px30 py10 text-center bgFA6C2F ml40 text28 radius50">去支付</view>
						<!-- 待收货 -->
						<view v-if="checkIndex==3" class="col-white px30 py10 text-center bg36A9FC ml40 text28 radius50">确认收货</view>
						<!-- 售后 -->
						<view v-if="checkIndex==4" class="colFA6C2F px30 py10 text-center borderFA6C2F ml40 text28 radius50" @click="handleVisable">申请售后</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 售后弹框 -->
		<view class="" @touchmove.stop.prevent="() => {}">
		<ch-picker ref="ChPicker" position="bottom" :columns="columns" :defaultIndex="curIndexs"
			@change="pickerChange"></ch-picker>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				checkIndex: 1,
				status: false, //收起展开状态
				curIndexs: [1],
				columns: [
					[{
							label: "退款",
							value: 1,
						}, {
							label: "换货",
							value: 2,
						}, {
							label: "退款退货",
							value: 3,
						},
					],
				],
			}
		},
		methods: {
			pickerChange(e) {
				// console.log(e);
				this.curIndexs = e.indexs
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleStatsu() {
				this.status = !this.status
			},
			handleIndex(index){
				this.checkIndex = index
			},
			handleVisable() {
				this.$refs.ChPicker.show()
			},
			

		}
	}
</script>

<style>
	.checkItem {
		width: 96rpx;
		height: 8rpx;
		background: linear-gradient(90deg, #FB6E19 0%, #EA0306 100%);
		border-radius: 10rpx;
	}
</style>