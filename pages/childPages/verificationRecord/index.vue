
<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="核销记录" color="#000000" @clickLeft="back" />
		</view>
		<view class="p30 bgF4F6F5">
			<view class="flex justify-between items-center">
				<view class="text28">核销记录</view>
				<view class="flex items-center" @click="handleCode()">
					<uni-icons type="scan" color="#FA6C2F" size="18"></uni-icons>
					<view class="colFA6C2F text20 ml20">扫一扫</view>
				</view>
			</view>
			<view class="py20 px30 mt20 flex justify-between items-center bg-white radius10" v-for="item in [1,2,3,4,5]" :key="item">
				<view class="flex items-center">
					<image src="https://img.picui.cn/free/2024/08/20/66c42b8cd4178.png" class="w60 h60" mode=""></image>
					<view class="ml20">
						<view class="text28 font-bold ">张三</view>
						<view class="text20">加入时间 2024-6-26</view>
					</view>
				</view>
				<view class="flex items-center ">
					<view class="text20 col333333">创造收益</view>
					<view class="text28 colFF0000 font-bold ml20">666666</view>
				</view>
			</view>
		</view>
		<view class="" @click="handleNumber">
			核销数量
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
			handleNumber(){
				uni.navigateTo({
					url: '/pages/childPages/verificationNumber/index'
				})
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleCode(){
				uni.scanCode({
					success: function (res) {
						console.log('条码类型：' + res.scanType);
						console.log('条码内容：' + res.result);
					}
				});
			}
		}
	}
</script>

<style>
	
	
</style>
