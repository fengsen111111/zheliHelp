<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="荣耀墙" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30 grid grid-cols-2">
			<image :class="item%2?'':'ml10'" src="https://img.picui.cn/free/2024/08/20/66c40375e02ec.png" class="imgItem" v-for="item in [1,2,3,4,5,6]" :key="item" mode=""></image>
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
			handleDetails() {
				uni.navigateTo({
					url: '/pages/childPages/cardDetails/index'
				})
			}
		}
	}
</script>

<style>
	.bgCard1 {
		background-image: url('@/static/user/bg.png');
		background-size: 100% 100%;
		height: 128rpx;
		width: 100%;
	}
	.imgItem{
		width: 99%;
		height: 340rpx;
		margin-top: 20rpx;
	}
</style>