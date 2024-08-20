<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="我的团队" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30 bgF4F6F5">
			<view class="headerUser flex items-center justify-between" style="background-image: url('https://img.picui.cn/free/2024/08/20/66c45f90d0782.png');">
				<view class="flex items-center">
					<image src="@/static/user/user.png" class="img88" mode=""></image>
					<view class="ml20 col-white">
						<view class="text28 font-bold">张三</view>
						<view class="text20">
							<text>成员</text>
							<text class="ml30">某某某社区/个人推广</text>
						</view>
					</view>
				</view>
				<view class="">
					<view class="flex items-center col-white">
						<view class="text20">总收入</view>
						<view class="text28 ml20">666666</view>
					</view>
					<view class="flex mt15 items-cneter col-white">
						<view class="text20">可提现</view>
						<view class="text24 ml20">666666</view>
					</view>
				</view>
			</view>
			<!--  -->
			<view class="bg-white flex justify-around text-center text20 p30 radius-bottom4">
				<view class="" @click="handleTo('/pages/childPages/payouts/index')">
					<image src="@/static/user/team1.png" class="img60" mode=""></image>
					<view class="mt15">提现</view>
				</view>
				<view class="" @click="handleTo('/pages/childPages/teamList/index')">
					<image src="@/static/user/team2.png" class="img60" mode=""></image>
					<view class="mt15">团队列表</view>
				</view>
				<view class="" @click="centerPay('center')">
					<image src="@/static/user/team3.png" class="img60" mode=""></image>
					<view class="mt15">推广码</view>
				</view>
			</view>
			<!--  -->
			<view class="bg-white radius12 mt20 text20 p30 ">
				<view class="text24">提现记录</view>
				<view class="flex justify-between items-center mt40" v-for="item in [1,3,4,5,6,7,8]" :key="item">
					<view class="text20">2024-06-26 12:26</view>
					<view class="text28 font-bold colFF0000">-66666</view>
				</view>
			</view>
			<!--  -->
			
		</view>
		<!-- 二维码 -->
		<uni-popup ref="popupCenter" background-color="#fff" borderRadius="20rpx 20rpx 20rpx 20rpx">
			<view class="radius20 bg-white p30" style="width: 70vw;">
				<view class="flex justify-between items-center">
					<view class="w28"></view>
					<view class="">推广二维码</view>
					<view>
						<uni-icons type="closeempty" size="20" color="#666666" @click="cancelCenterPay"></uni-icons>
					</view>
				</view>
				<view class="text-center mt30 p30">
					<image src="@/static/user/QRcode2.png" class="w-full h500 " mode=""></image>
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		methods: {
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleTo(url){
				uni.navigateTo({
					url: url
				})
			},
			centerPay(type) {
				this.type = type
				this.$refs.popupCenter.open(type)
			},
			cancelCenterPay() {
				this.$refs.popupCenter.close()
			},
		}
	}
</script>

<style>
	.headerUser{
		
		background-size: 100% 100%;
		height: 100rpx;
		padding:20rpx;
	}
	.img60{
		width: 60rpx;
		height: 60rpx;
	}
	
</style>
