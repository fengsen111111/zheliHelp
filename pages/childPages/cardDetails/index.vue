<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="详情" color="#000000" @clickLeft="back" />
		</view>
		<view class="px30 ">
			<view class="mt40" v-for="item in [1,2,3,4,5,6,7,8]" :key="item" >
				<view class="flex justify-between items-center">
					<view class="flex items-center">
						<image v-if="item%2" src="@/static/user/iconGreen.png" class="w60 h60" mode=""></image>
						<image v-else src="@/static/user/iconOrange.png" class="w60 h60" mode=""></image>
						<view class="ml20 col333333">
							<view class="text24 font-bold">在线充值</view>
							<view class="text20 mt5">2024-06-26 12:26</view>
						</view>
					</view>
					<view class="colFF0000 text30 font-bold">
						{{item%2?'+666666':'-666666'}}
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
			
			}
		},
		methods: {
		
			back() {
				console.log('返回')
				uni.navigateBack()
			},
		
		}
	}
</script>

<style>
	.bgCard1{
		
		background-size: 100% 100%;
		/* height: 320rpx; */
		width: 100%;
	}
</style>