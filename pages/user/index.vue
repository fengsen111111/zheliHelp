<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="个人中心" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30 bgF4F6F5">
			<view class="headerUser flex items-center justify-between">
				<view class="flex items-center">
					<image src="@/static/user/user.png" class="img88" mode=""></image>
					<view class="ml20 col-white">
						<view class="text28 font-bold">默认昵称</view>
						<view class="text24">123****1234</view>
					</view>
				</view>
				<view class="borderDCC896 colDCC896 text24 radius4 px10 py5 " @click="handleTo('/pages/childPages/userRechange/index')">
					会员充值
				</view>
			</view>
			<!--  -->
			<view class="bg-white grid grid-cols-4 text-center text24 p30 radius-bottom4" @click="handleOrderList">
				<view class="">
					<image src="@/static/user/status1.png" class="img50" mode=""></image>
					<view class="mt15">待付款</view>
				</view>
				<view class="">
					<image src="@/static/user/status2.png" class="img50" mode=""></image>
					<view class="mt15">待发货</view>
				</view>
				<view class="">
					<image src="@/static/user/status3.png" class="img50" mode=""></image>
					<view class="mt15">待收货</view>
				</view>
				<view class="">
					<image src="@/static/user/status4.png" class="img50" mode=""></image>
					<view class="mt15">售后</view>
				</view>
			</view>
			<!--  -->
			<view class="bg-white radius12 grid grid-cols-4 mt20 text-center text24 p30 radius-bottom4">
				<view class="mb30" @click="handleTo('/pages/childPages/myCard/index')">
					<image src="@/static/user/icon1.png" class="img50" mode=""></image>
					<view class="mt15">我的卡包</view>
				</view>
				<view class="mb30" @click="handleTo('/pages/childPages/loveExchange/index')">
					<image src="@/static/user/icon2.png" class="img50" mode=""></image>
					<view class="mt15">爱心兑换</view>
				</view>
				<view class="mb30" @click="handleTo('/pages/childPages/myTeam/index')">
					<image src="@/static/user/icon3.png" class="img50" mode=""></image>
					<view class="mt15">我的团队</view>
				</view>
				<view class="mb30" @click="handleTo('/pages/childPages/colonelFiled/index')">
					<image src="@/static/user/icon4.png" class="img50" mode=""></image>
					<view class="mt15">团长管理</view>
				</view>
				<view class="" @click="handleTo('/pages/childPages/address/index')">
					<image src="@/static/user/icon5.png" class="img50" mode=""></image>
					<view class="mt15">地址管理</view>
				</view>
				<view class="" @click="handleTo('/pages/childPages/giftCardRecord/index')">
					<image src="@/static/user/icon6.png" class="img50" mode=""></image>
					<view class="mt15">礼品卡记录</view>
				</view>
				<view class="" @click="handleTo('/pages/childPages/merchantSettled/index')">
					<image src="@/static/user/icon7.png" class="img50" mode=""></image>
					<view class="mt15">商家入驻</view>
				</view>
				<view class="" @click="handleTo('/pages/childPages/merchantSettledIn/index')">
					<image src="@/static/user/icon8.png" class="img50" mode=""></image>
					<view class="mt15">厂家入驻</view>
				</view>
			</view>
			<!--  -->
			<view class="mt30 text26">
				<view @click="handleTo('/pages/childPages/giftCardOpen/index')" class="card mb20 px30 py14 items-center flex justify-between ">
					<view class="">礼品卡启用</view>
					<uni-icons type="right" size="20" color="#FA6C2F"></uni-icons>
				</view>
				<view @click="handleTo('/pages/childPages/verificationRecord/index')" class="card mb20 px30 py14 items-center flex justify-between ">
					<view class="">爱心核销</view>
					<uni-icons type="right" size="20" color="#FA6C2F"></uni-icons>
				</view>
				<view @click="handleTo('/pages/childPages/verificationRecordTwo/index')" class="card mb20 px30 py14 items-center flex justify-between ">
					<view class="">超市/驿站核销</view>
					<uni-icons type="right" size="20" color="#FA6C2F"></uni-icons>
				</view>
				<view @click="handleTo('/pages/childPages/feedback/index')" class="card mb20 px30 py14 items-center flex justify-between ">
					<view class="">意见反馈</view>
					<uni-icons type="right" size="20" color="#FA6C2F"></uni-icons>
				</view>
			</view>
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
			handleOrderList(){
				uni.navigateTo({
					url:'/pages/childPages/orderList/index'
				})
			},
			handleTo(url){
				uni.navigateTo({
					url: url
				})
			}
		}
	}
</script>

<style>
	.headerUser{
		background-image: url('@/static/user/bg.png');
		background-size: 100% 100%;
		height: 100rpx;
		padding:20rpx;
	}
	
</style>
