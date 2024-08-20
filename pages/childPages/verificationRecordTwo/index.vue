
<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="核销报告" color="#000000" @clickLeft="back" />
		</view>
		<view class="mt30 bg-white p30">
			<view class="flex w-full justify-between items-center">
				<view class="w-4-5">
					<view class="flex justify-between items-center">
						<view class="text30">核销总额</view>
						<view class="colFF0000 text36 font-bold">6666666</view>
					</view>
					<view class="text24 mt20 flex justify-between items-center">
						<view class="flex items-center">
							<text>月核销</text>
							<view class="bgF4F6F5 text20 py6 px20 text-center flex items-center">
								<text>六月</text>
								<uni-icons type="down" class="ml20" color="#FA6C2F" size="18"></uni-icons>
							</view>
						</view>
						<view class="colFF0000 text28 font-bold">6666666</view>
					</view>
				</view>
				<view class="bgFA6C2F  radius12 text-center p20" @click="handleCode()">
					<image src="@/static/user/code-s.png" class="w50 h50" mode=""></image>
					<view class="col-white text20">扫一扫</view>
				</view>
			</view>
		</view>
		<view class="p30 mt30 bg-white">
			<view class="py20 px30 mt20 flex justify-between items-center bg-white radius10" v-for="item in [1,2,3,4,5]" :key="item">
				<view class="flex items-center">
					<image src="https://img.picui.cn/free/2024/08/20/66c42b8cd4178.png" class="w60 h60" mode=""></image>
					<view class="ml20">
						<view class="text28 font-bold ">张三</view>
						<view class="text20">加入时间 2024-6-26</view>
					</view>
				</view>
				<view class="">
					<view class="">
						<view class="text20 col333333 ml140">员工卡</view>
					</view>
					<view class="flex items-center ">
						<view class="text20 col333333">创造收益</view>
						<view class="text28 colFF0000 font-bold ml20">666666</view>
					</view>
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
			},
			handleNumber(){
				uni.navigateTo({
					url: '/pages/childPages/verificationNumber/index'
 				})
			}
		}
	}
</script>

<style>
	
	
</style>
