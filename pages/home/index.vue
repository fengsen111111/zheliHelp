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
		  <view class="mt20">
		  	<view class="flex col999999">
		  		<view class="col-black text32 font-bold">
					推荐商品
					<view class="checkItem mx-auto"></view>
					</view>
		  		<view class="ml100">团购</view>
		  		<view class="ml100">组合套餐</view>
		  	</view>
			<!-- 推荐商品 -->
			<view class="">
				<view class="mt10 flex text24" styule="">
					<view class="tags" :class="item == 1?'col-black':'col999999'" v-for="item in [1,2,3,4,5]" :key="item">热门</view>
				</view>
				<view class=" grid grid-cols-2">
					 <shopItem v-for="item in [1,2,3,4]" :key="item"/>
				</view>
			</view>
			<!-- 团购 -->
			<view class=""></view>
			<!-- 组合套餐 -->
			<view class=""></view>
		  </view>
		 
	    </view>
	
	</view>
</template>

<script>
	import headerView from '@/components/headerView/index.vue'
	import tagCard from './components/tagCard/index.vue'
	import shopItem from './components/shopItem/index.vue'
	export default {
		components:{
			headerView,tagCard,shopItem
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
	.tags{
		width: 300px;
		text-align: center;

	}
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
