<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="我的卡包" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30">
			<view class="bgCard1 colDCC896 " style="background-image: url('../../../static/user/card1.png');">
				<view class="flex items-center justify-between p30">
					<view class="flex items-center">
						<image src="@/static/home/pay2.png" class="w62 h50" mode=""></image>
						<view class="text40 font-bold ml10">VIP</view>
					</view>
				    <view class="flex items-center ">
	    				<view class="text24">余额</view>
			    		<view class="text36 font-bold ml10">￥88888.88</view>
		    			<image src="@/static/user/QRcode1.png" class="w50 h50 ml20" mode=""></image>
		    		</view>
				</view>
				<view class=" px30 pt10 pb30 col999999 text20">
					<view class="">说明</view>
					<view class="">会员管理制度应包括发行人及会员的权利和义务、会员卡的管理方 式、会员参与管理的组织形式、会员卡资金管理、会籍的转让和继 承、年费缴纳等。保护了会员的权益，与消费者之间的良好关系。</view>
					<view class="mt20 float-right items-center flex colDCC896" @click="handleDetails">
						<text>详情</text>
						<uni-icons type="right" size="18" class="mt5" color="#DCC896"></uni-icons>
					</view>
					<view class="h50"></view>
				</view>
			</view>
			<!-- 2 -->
			<view class="bgCard1 mt40" style="background-image: url('../../../static/user/card2.png');">
				<view class="flex items-center justify-between p30">
					<view class="flex items-center">
						<image src="@/static/home/pay3.png" class="w50 h50" mode=""></image>
						<view class="text40 font-bold ml10 col36A9FC">员工卡</view>
					</view>
				    <view class="flex items-center ">
						<view class="text24">余额</view>
			    		<view class="text36 font-bold ml10">￥88888.88</view>
						<image src="@/static/user/QRcode2.png" class="w50 h50 ml20" mode=""></image>
					</view>
				</view>
				<view class=" px30 pt10 pb30 col999999 text20 ">
					<view class="">说明</view>
					<view class="">会员管理制度应包括发行人及会员的权利和义务、会员卡的管理方 式、会员参与管理的组织形式、会员卡资金管理、会籍的转让和继 承、年费缴纳等。保护了会员的权益，与消费者之间的良好关系。</view>
					<view class="mt20 col36A9FC items-center float-right flex" @click="handleDetails"> 
						<text>详情</text>
						<uni-icons type="right" size="18" class="mt5" color="#36A9FC"></uni-icons>
					</view>
					<view class="h50"></view>
				</view>
			</view>
			<!-- 3 -->
			<view class="bgCard1 mt40" style="background-image: url('../../../static/user/card3.png');">
				<view class="flex items-center justify-between p30">
					<view class="flex items-center">
						<view class="w50 h50"><image src="@/static/home/pay42.png" class="w50 h50" mode=""></image></view>
						<view class="text40 font-bold ml10 col-white">老年卡</view>
					</view>
				    <view class="flex items-center col-white">
						<view class="text24">余额</view>
			    		<view class="text36 font-bold ml10">￥88888.88</view>
						<image src="@/static/user/QRcode3.png" class="w50 h50 ml20" mode=""></image>
					</view>
				</view>
				<view class=" px30 pt10 pb30 col666666 text20 ">
					<view class="">说明</view>
					<view class="">会员管理制度应包括发行人及会员的权利和义务、会员卡的管理方 式、会员参与管理的组织形式、会员卡资金管理、会籍的转让和继 承、年费缴纳等。保护了会员的权益，与消费者之间的良好关系。</view>
					<view class="mt20 col-white items-center float-right flex" @click="handleDetails">
						<text>详情</text>
						<uni-icons type="right" size="18" color="#FFFFFF" class="mt5"></uni-icons>
					</view>
					<view class="h50"></view>
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
		
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleDetails(){
				uni.navigateTo({
					url:'/pages/childPages/cardDetails/index'
				})
			}
		}
	}
</script>

<style>
	.bgCard1{
		
		background-size: 100% 100%;
		/* height: 320rpx; */
		width: 100%;
	}
</style>