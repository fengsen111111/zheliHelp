<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="爱心兑换" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30">
			<view class="bgCard1 ">
				<view class="p20 col-white items-center flex justify-between">
					<view class="">
						<view class="flex items-center">
							<view class="text20">总爱心值</view>
							<view class="text28 font-bold ml20">666666</view>
						</view>
						<view class="flex items-center">
							<view class="text20">可兑换</view>
							<view class="text24 font-bold ml30">666666</view>
						</view>
					</view>
					<view class="flex items-center">
						<view class="text20">爱心等级</view>
						<view class="text20 ml20">Level</view>
						<view class="text32 uni-ml-2">1</view>
						<view class="ml40">
							<image src="@/static/user/QRcode3.png" class="w50 h50 mt5" mode=""></image>
						</view>
					</view>
				</view>
			</view>
			<!--  -->
			<view class="mt20 flex justify-between">
				<image src="@/static/home/leftImg.png" class="imgLeftRight" mode=""
					@click="handeVicinty"></image>
				<image src="@/static/home/rightImg.png" @click="handleDetails" class="imgLeftRight" mode=""
					></image>
			</view>
			
		</view>
		<view class="bg-white py20 px50">
			<view class="flex justify-between items-center mb20" v-for="item in [1,2,3,4]" :key="item">
				<view class="">
					<view class="text24 font-bold">消费获得</view>
					<view class="text20 mt5">2024-06-26 12:26</view>
				</view>
				<view class="text30 font-bold colFF0000">+66666</view>
			</view>
			<view class="h206"></view>
			<view class="h206"></view>
			<view class="h206"></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			handeVicinty() {
				uni.navigateTo({
					url: '/pages/childPages/authentication/index'
				})
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleDetails() {
				uni.navigateTo({
					url: '/pages/childPages/glory/index'
				})
			}
		}
	}
</script>

<style>
	.imgLeftRight{
		width: 49%;
		height: 128rpx;
	}
	.bgCard1 {
		background-image: url('@/static/user/bg.png');
		background-size: 100% 100%;
		/* height: 128rpx; */
		width: 100%;
	}
</style>