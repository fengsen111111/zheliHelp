
<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="我的团队" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30 bgF4F6F5">
			<view class="py20 px30 mb20 flex justify-between items-center bg-white radius10" v-for="item in [1,2,3,4,5]" :key="item">
				<view class="flex items-center">
					<image src="https://img.picui.cn/free/2024/08/20/66c42b8cd4178.png" class="w60 h60" mode=""></image>
					<view class="ml20">
						<view class="text28 font-bold ">张三</view>
						<view class="text20">加入时间 2024-6-26</view>
					</view>
				</view>
				<view class="flex items-center col333333">
					<view class="text20">创造收益</view>
					<view class="text28 font-bold ml20">666666</view>
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
	
	
</style>
