<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="团购详情" color="#000000" @clickLeft="back" />
		</view>
		<!-- 轮播 -->
		<view class="relative">
			<swiper class="swiper" style="height: 600rpx !important;" :current="current" :indicator-dots="false" :autoplay="false">
				<swiper-item v-for="(item,index) in imgList" :key="index">
					<image :src="item.url" mode="" class="w-full h600"></image>
				</swiper-item>
			</swiper>
			<view class="bg-black flex p20 w-full h120 opacity6 absolute bottom0">
				<view class="" v-for="(item,index) in imgList" :key="index">
					<image :src="item.url" mode="" class="w120 radius12 h120 mr20" @click="handleIndex(index)" :class="current==index?'borderFA6C2F-8':''"></image>
				</view>
			</view>
		</view>
		<!--  -->
		<view class="mt10 px30 bg-white pb14">
			<view class="text36 flex items-center">
				<view class="mr20 colFF0000">￥8888</view>
				<view class="col666666 text24 delText ml20">￥6666</view>
			</view>
			<view class="text30 font-bold">
				陈昌银重庆磁器口精品豪华陈麻花八合一组合零食干货大礼包
			</view>
			<view class="flex mt10 justify-between text28 col666666">
				<view class="flex">
					<view class="">剩余数量</view>
					<view class="ml20">88888</view>
				</view>
				<view class="flex">
					<view class="">已购数量</view>
					<view class="ml20">66666</view>
				</view>
			</view>
		</view>
		<!--  -->
		<view class="mt20 bg-white px30 py20">
			<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w-full h328" mode=""></image>
			<view class="mt20 text24">
				本土特产提供者食济良作为重庆特产行业的代表性企业，从事特产行业十余年，线下实体店的规模在重庆排名独占鳌头，拥有连锁分店30多家，特产产品超过500种。
			</view>
		</view>
		<!-- 留白 -->
		<view class="h160"></view>
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
			}
		}
	}
</script>

<style>
</style>