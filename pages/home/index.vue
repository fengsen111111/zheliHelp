<template>
	<view class="">
		<!-- 公用头部 -->
		<headerView />
		<!-- 轮播图 -->
	    <view class="p30 relative -top60">
		  <swiper class="swiper " circular :indicator-dots="true" :autoplay="false" :interval="3000" :duration="500">
			<swiper-item v-for="item in [1,2,3,4]" :key="item">
				<image src="https://img.erpweb.eu.org/imgs/2024/08/f4cff88abfbb611e.png" class="w-full h-full radius20" mode=""></image>
			</swiper-item>
		  </swiper>
		  <!-- card -->
		  <view class="mt20">
		  	<tagCard />
		  </view>
		  <!-- left right -->
		  <view class="mt20 flex justify-between">
			  <image src="@/static/home/leftImg.png" class="imgLeftRight" mode=""></image>
			  <image src="@/static/home/leftImg.png"  class="imgLeftRight" mode=""></image>
		  </view>
		  <!-- tabs -->
		  <homeBottom />
		 
	    </view>
	
	</view>
</template>

<script>
	import headerView from '@/components/headerView/index.vue'
	import tagCard from './components/tagCard/index.vue'
	import homeBottom from './components/homeBottom/index.vue'
	export default {
		components:{
			headerView,tagCard,homeBottom
			},
		data() {
			return {
				
			}
		},
		methods: {

		}
	}
</script>

<style>
	.imgLeftRight{
		width: 49%;
		height: 128rpx;
	}
	.checkItem{
		width: 96rpx;
		height: 8rpx;
		background: linear-gradient( 90deg, #FB6E19 0%, #EA0306 100%);
		border-radius: 10rpx;
	}
</style>
