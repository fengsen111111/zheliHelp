<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff"  status-bar left-icon="left"
				title="采集登记介绍" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="p30">
			<image src="https://img.picui.cn/free/2024/08/19/66c2e7c4175b9.png" class="w-full h483" mode=""></image>
			<view class="col333333 text24">
				本土特产提供者食济良作为重庆特产行业的代表性企业，从事特 产行业十余年，线下实体店的规模在重庆排名独占鳌头，拥有连 锁分店30多家，特产产品超过500种。
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