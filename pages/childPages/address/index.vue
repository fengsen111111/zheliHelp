<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="地址管理" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30">
			<view class="bg-white radius12 mb20" v-for="item in [1,2,3,4]" :key="item">
				<view class="p20 text24">
					<view class="flex items-center ">
						<view class="">张三</view>
						<view class="ml10">12312341234</view>
					</view>
					<view class="flex items-center justify-between">
						<view class="">
							<view class="">四川省-成都市-武侯区</view>
							<view class="">世纪城天府大道中段588号</view>
						</view>
						<view class="flex items-center">
							<uni-icons type="compose" color="#36A9FC" size="20"></uni-icons>
							<uni-icons type="trash" color="#FF0000" class="ml40" size="20"></uni-icons>
						</view>
					</view>
				</view>
				<view class="bg999999 h1 w-full"></view>
				<view class="p20 text24 flex items-center">
					<uni-icons type="circle" color="#666666" size="20"></uni-icons>
					<view class="col333333 ml20">默认收货地址588号</view>
				</view>
			</view>
		</view>
		<!-- 底部固定 -->
		<view class="fixed bottom0 w-full bg-white">
			<view class="py30 px75">
				<view class="bg36A9FC col-white text28 font-bold text-center py14 radius12" @click="handleAdd">
					新增地址
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {
			handleAdd(){
				uni.navigateTo({
					url:'/pages/childPages/addressAdd/index'
				})
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