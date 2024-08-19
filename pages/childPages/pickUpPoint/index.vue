<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="选择自提点" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30">
			<view class="bg-white col999999 flex items-center p20 text28 radius50">
				<uni-icons type="search" size="20" class="mr20"></uni-icons>
				<input type="text" placeholder="搜索自提点"/>
			</view>
			<!--  -->
			<view class="mt30 p20 relative flex justify-between items-center bg-white radius12" v-for="item in [1,2,3]" :key="item">
				<!-- 小标 -->
				<view class="bgFA6C2F col-white font-bold text24 px10 absolute top0 right0" :class="item == 1?'radio-right-top12':''" v-if="item==1">
					当前选择
				</view>
				<view class="">
					<image src="https://img.picui.cn/free/2024/08/19/66c2bb92d8844.png" class="w120 h120 radius12" mode=""></image>
				</view>
				<view class="ml20">
					<view class="text24">沃尔玛超市</view>
					<view class="text20 col999999">联系人：张三 12312341234</view>
					<view class="text20 col999999">四川省成都市武侯区桂溪街道桂溪街道世纪城南路67号</view>
				</view>
				<view class="text-center">
					<view class=""><uni-icons type="location" size="20" class=""></uni-icons></view>
					<view class="text20 col999999">888km</view>
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data(){
			return {
			}
		},
		methods:{
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			
		}
	}
</script>

<style>
</style>