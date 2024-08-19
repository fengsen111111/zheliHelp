<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="商品详情" color="#000000" @clickLeft="back" />
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
		<view class="mt10 px30  bg-white pb14">
			<view class="text36 flex justify-between w-full items-center">
				<view class="flex items-center">
					<view class="mr20 colFF0000">￥8888</view>
					<view class="col666666 text24 delText ml20">￥6666</view>
				</view>
				<view class="borderFF0000 text28 px10 radius10 font-bold colFF0000">
					员工自提
				</view>
			</view>
			<view class="text30 font-bold">
				陈昌银磁器口陈麻花
			</view>
			<view class="flex mt10 text20">
				<view class="flex">
					<view class="bgFA6C2F col-white px10 line30 radius4">
						销量
					</view> 
					<view class="colFA6C2F bg-white px10 line30 radius4 borderFA6C2F">
						6666
					</view>
				</view>
				<view class="flex ml20">
					<view class="bg36A9FC  col-white px10 line30 radius4">
						产地
					</view> 
					<view class="col36A9FC  bg-white px10 line30 radius4 border36A9FC ">
						石家庄
					</view>
				</view>
			</view>
			<view class="mt20 text24">
				<text>本土特产提供者食济良作为重庆特产行业的代表性企业，从事特产行业十余年，线下实体店的规模在重庆排名独占鳌头，拥有连锁分店30多家，特产产品超过500种。</text>
				<text class="colFA6C2F ml20">展开</text>
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
		<!-- 固定 -->
		<view class="">
			<view class="flex px30 py14 items-center justify-between fixed bottom0 bg-white">
				<view class="flex">
					<view class=""><image src="@/static/home/collect.png" mode="" class="w60 h60"></image></view>
					<view class="ml60"><image src="@/static/home/server.png" mode="" class="w60 h60"></image></view>
				</view>
				<view class="flex ml150">
					<view class="borderFA6C2F colFA6C2F radius12 bg-white text-center p20">加入购物车</view>
					<view class="bgFA6C2F col-white radius12 text-center p20 ml20" @click="handleSubmit">立即购买</view>
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
			handleSubmit(){
				uni.navigateTo({
					url: '/pages/childPages/shopSubmitOrder/index'
				})
			}
		}
	}
</script>

<style>
</style>