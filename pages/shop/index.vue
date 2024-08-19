<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="商品" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class=" flex text24">
			<view class="bgF4F6F5  w-1-4">
				<view class="colFA6C2F px44 py22">饮料类</view>
				<view class="col999999 px44 py22">生活类</view>
				<view class="col999999 px44 py22">粮油类</view>
				<view class="col999999 px44 py22">生活类</view>
				<view class="col999999 px44 py22">粮油类</view>
				<view class="col999999 px44 py22">生活类</view>
				<view class="col999999 px44 py22">粮油类</view>
			</view>
			<view class="w-3-4 radius20 bg-white p30 text20">
				<view class="flex justify-between">
					<view class="flex items-center">
						<view class="">产地</view>
						<view class="bgF4F6F5 flex items-center w140 text-center ml10">
							<view class="mx-auto">全部</view> 
							<uni-icons type="down" size="20" class="colFA6C2F"></uni-icons>
						</view>
					</view>
					<view class="flex" @click="handleSold()">
						<view class="mr10">销量</view>
					    <image src="@/static/shop/search.png" class="w20 h28" v-if="search.sold==1" mode=""></image>
					    <image src="@/static/shop/searchUp.png" class="w20 h28" v-else-if="search.sold==2"  mode=""></image>
					    <image src="@/static/shop/searchDown.png" class="w20 h28" v-else-if="search.sold==3"  mode=""></image>
					</view>
					<view class="flex" @click="handlePrice()">
						<view class="mr10">价格</view>
					    <image src="@/static/shop/search.png" class="w20 h28" v-if="search.price==1" mode=""></image>
					    <image src="@/static/shop/searchUp.png" class="w20 h28" v-else-if="search.price==2"  mode=""></image>
					    <image src="@/static/shop/searchDown.png" class="w20 h28" v-else-if="search.price==3"  mode=""></image>
					</view>
				</view>
				<view class="mt30 flex " v-for="item in [1,2,3,4,5,6]" :key="item" @click="handleDetails">
					<image src="https://imgos.cn/2024/08/16/66bea893084a3.png" class="img200" mode=""></image>
					<view class="ml20 w290">
						<view class="text24 font-bold ">面包糠1kg大包装面包屑炸鸡粉炸鸡裹 鸡排面包康</view>
						<view class="flex mt10">
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
						<view class="flex mt10 col999999">金皇花 面包糠1kg大包装面包屑炸鸡粉炸鸡裹粉肯德基...</view>
						<view class="mt10 text32 colFF0000 font-bold">
							￥888.88
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				search:{
					sold:1,
					price:1
				}
			}
		},
		methods: {
			handleDetails(){
				uni.navigateTo({
					url: '/pages/childPages/shopDetails/index'
				})
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleSold(){
				if(this.search.sold==1){
					this.search.sold = 2
				}else if(this.search.sold==2){
					this.search.sold = 3
				}else if(this.search.sold==3){
					this.search.sold = 2
				}
			},
			handlePrice(){
				if(this.search.price==1){
					this.search.price = 2
				}else if(this.search.price==2){
					this.search.price = 3
				}else if(this.search.price==3){
					this.search.price = 2
				}
			}
		}
	}
</script>

<style>
</style>