<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="团长管理" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30 flex justify-between items-center bg-white mt20">
			<view class="flex items-center">
				<view class="text30">可提现</view>
				<view class="text30 colFF0000 ml30">666666</view>
			</view>
			<view class="flex text28 font-bold col-white items-center">
				<view class="bgFA6C2F radius10 px20 py10" @click="handleWithdraw">提现</view>
				<view class=" bg36A9FC radius10 ml40 px20 py10" @click="handleDetails">详情</view>
			</view>
		</view>
		<view class="px30">
			<view class="pt20 text24 col333333 font-bold">今日订单</view>
			<view class="mt10 grid text-center grid-cols-2">
				<view class="text32 ">
					<view class="col333333">自提</view>
					<view class="bgFA6C2F h1 mx-auto w86 mt5"></view>
				</view>
				<view class="text32  ">
					<view class="col999999">上门</view>
				</view>
			</view>
			<!--  -->
			<view class="py20 text24 bg-white radius10 mt30" v-for="item in [1,2,3]" :key="item">
				<view class="px20">
					<view class="mt20 ">用户地址</view>
					<view class="mt10 ">四川省成都市武侯区桂溪街道桂溪街道桂溪街道世纪城南路 67号</view>
				</view>
				<view class="bg999999 h1 mt10"></view>
				<view class="px20">
					<view class="mt10">商品信息</view>
					<view class="mt20 flex justify-between items-center" v-for="item in [1,2,3]" :key="item">
						<view class="">
							<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w100 h100 radius12"
								mode=""></image>
						</view>
						<view class="ml20">
							<view class="">陈昌银重庆磁器口精品豪华陈麻花百草味藕片零食</view>
							<view class="col999999">袋装(500g)</view>
						</view>
						<view class="col333333 text30 ml20">X666</view>
					</view>
					<view class="mt40 px30">
						<view class="font-bold radius10 text36 py10 bg36A9FC text-center col-white">
							已自提
						</view>
						<view class="font-bold radius10 text36 py10 bgFA6C2F text-center col-white">
							已送达
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleDetails(){
				uni.navigateTo({
					url:'/pages/childPages/cardDetails/index'
				})
			},
			handleWithdraw(){
				uni.navigateTo({
					url:'/pages/childPages/withdraw/index'
				})
			}

		}
	}
</script>

<style>
</style>