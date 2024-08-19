<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="套餐详情" color="#000000" @clickLeft="back" />
		</view>
		<!-- 轮播 -->
		<view class="relative">
			<swiper class="swiper" style="height: 600rpx !important;" :current="current" :indicator-dots="false" :autoplay="false">
				<swiper-item v-for="(item,index) in imgList" :key="index">
					<image :src="item.url" mode="" class="w-full h600"></image>
				</swiper-item>
			</swiper>
		</view>
		<!--  -->
		<view class="mt10 px30 bg-white pb14">
			<view class="text30 mt20 font-bold">
				陈昌银重庆磁器口精品豪华陈麻花八合一组合零食干货大礼包
			</view>
			<view class="flex mt20 text24 mb30 col666666">
				<view class="">
					百草味藕片+百草味蟹黄蚕豆+脆升升薯条+纳宝帝丽巧克+威化饼干+可比克+娃哈哈AD钙奶+阿尔卑斯葡萄糖果+喜...
					<text class="colFA6C2F">展开</text>
				</view>
			</view>
		</view>
		<!--  -->
		<view class="mt10 pt20 px30 bg-white pb14">
			<view class="text30 mt20 font-bold">
				商品列表
			</view>
			<view class="flex items-center mt20 ml20 text24 mb30 col666666" v-for="item in [1,2,3]" :key="item">
				<view class="">
					<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w100 h100 radius12" mode=""></image>
				</view>
				<view class="ml20">
					<view class="">陈昌银重庆磁器口精品豪华陈麻花百草味藕片零食</view>
					<view class="col999999">袋装(500g)</view>
				</view>
				<view class="col333333 text30 ml20 font-bold">X666</view>
			</view>
		</view>
		<!-- 留白 -->
		<view class="h160"></view>
		<!-- 固定 -->
		<view class="">
			<view class="flex w-full py14 items-center justify-between fixed bottom0 bg-white">
				<view class="flex items-center ml30">
					<view class="text30">套餐价</view>
					<view class="colFF0000 text40 font-bold ml20">￥6666</view>
				</view>
				<view class="flex mr30 items-center">
					<view class="ml60"><image src="@/static/home/send.png" mode="" class="w60 h60"></image></view>
					<view class="bgFA6C2F col-white radius12 text-center p20 ml40">去下单</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				current:2,//当前轮播图
				imgList: [{
						url: 'https://img.picui.cn/free/2024/08/16/66bf089662182.png'
					},
					{
						url: 'https://imgos.cn/2024/08/16/66bee55d2820e.png'
					},
					{
						url: 'https://imgos.cn/2024/08/16/66befac82d157.png'
					},
					{
						url: 'https://imgos.cn/2024/08/16/66bee55d2820e.png'
					},
				],
			}
		},
		methods: {
			onChange(item, index) {
				console.log(item)
				console.log(index)
			},
			handleIndex(index){
				console.log('12313123',index)
				this.current = index
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
		}
	}
</script>

<style>
</style>