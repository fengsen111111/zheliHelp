<template>
	<view class="headerBg" style="background-image: url('../../static/home/headerBg.png');">
		<!-- 自定义导航栏 -->
			<view class="navBarBox">
				<!-- 状态栏占位 -->
				<view class="statusBar" :style="{ paddingTop: statusBarHeight + 'px' }">
				</view>
				<!-- 真正的导航栏内容 -->
				<view class="navBar">
					<view class="">
						<image src="@/static/home/hraderText.png" class="imgText" mode=""></image>
					</view>
					<view class="bg-white flex col999999 items-cneter p20 mt36 radius50">
						<uni-icons type="search" size="24" color="#999999"></uni-icons>
						<view>输入关键词搜索商品</view>
					</view>
				</view>
			</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 状态栏高度
				statusBarHeight: 0,
				// 导航栏高度
				navBarHeight: 82 + 11,
			};
		},
		created() {
			//获取手机状态栏高度
			this.statusBarHeight = uni.getSystemInfoSync()['statusBarHeight'];
		},
		
	}
</script>

<style>
	.imgText{
		width: 174rpx;
		height: 64rpx;
	}
	.headerBg{
		background-size: 100% 100%;
		width: 100%;
		height: 280rpx
	}
	navBarBox {}
	
	.navBarBox .statusBar {}
	
	.navBarBox .navBar {
		padding-bottom: 8rpx;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		padding-left: 30rpx;
		padding-right: 30rpx;
	}
</style>