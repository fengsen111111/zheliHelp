<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="礼品卡记录" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30">
			<view class="bg-white py20 radius12 ,mb20" v-for="item in [1,2,3,4,5]" :key="item">
				<view class="px20 flex items-center justify-between">
					<view class="text24 font-bold ">订单编号:123456789</view>
					<view class="text20 ">下单时间 2024-06-26</view>
				</view>
				<view class="h1 bg999999 w-full mt20"></view>
				<view class="mt20 px20 text24">您的快递已到四川省成都市武侯区世纪城天府大道中段588号天天小区快鸟驿站</view>
				<view class="h1 bg999999 w-full mt20"></view>
				<view class="px20 mt20">
					<view class="flex items-center justify-between">
						<view class="text24 font-bold">商品信息</view>
						<view class="text20 colFA6C2F" @click="handUpDown">{{status?'收起':'展开'}}</view>
					</view>
					<view class="" v-if="status">
						<view class="mt20 flex justify-between items-center" v-for="item in [1,2,3]" :key="item">
							<view class="">
								<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w100 h100 radius12"
									mode=""></image>
							</view>
							<view class="ml20 text24">
								<view class="">陈昌银重庆磁器口精品豪华陈麻花百草味藕片零食</view>
								<view class="col999999">袋装(500g)</view>
							</view>
							<view class="col333333 text30 ml20">X666</view>
						</view>
					</view>
				</view>
				<!-- 留白 -->
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				status: true
			}
		},
		methods: {
			back() {
				console.log('返回')
				uni.navigateBack()
			},
            handUpDown(){
				this.status = !this.status
			}
		}
	}
</script>

<style>
</style>