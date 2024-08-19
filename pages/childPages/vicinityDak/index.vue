<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="附近驿站/超市" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30">
			<view class="bg-white col999999 flex items-center p20 text28 radius50">
				<uni-icons type="search" size="20" class="mr20"></uni-icons>
				<input type="text" placeholder="搜索自提点" />
			</view>
			<!--  -->
			<view class="flex justify-between mt20">
				<view class=""></view>
				<view class="bg-white text20 py6 px20 radius10 items-center flex">
					<text>全部</text>
					<uni-icons type="down" size="20" color="#FA6C2F" class="ml20"></uni-icons>
				</view>
			</view>
			<!--  -->
			<view class="" v-for="item in [1,2,3]" :key="item">
				<view class="mt20 p20 flex justify-between items-center bg-white radiusTop12">
					<view class="">
						<image src="https://img.picui.cn/free/2024/08/19/66c2bb92d8844.png" class="w120 h120 radius12"
							mode=""></image>
					</view>
					<view class="ml20">
						<view class="flex justify-between">
							<view class="text24">沃尔玛超市</view>
							<view class="flex text20">
								<view class="col36A9FC">员工</view>
								<view class="colDDC899 ml20">会员</view>
								<view class="col68BF7B ml20">线下</view>
							</view>
						</view>
						<view class="text20 col999999">联系人：张三 12312341234</view>
						<view class="text20 col999999">四川省成都市武侯区桂溪街道桂溪街道世纪城南路67号</view>
					</view>
					<view class="text-center">
						<view class=""><uni-icons type="location" size="20" class=""></uni-icons></view>
						<view class="text20 col999999">888km</view>
					</view>
				</view>
				<view class="p20 col999999 radiusBottom12 text20 borderTop999999 bg-white">
					作为世界上最大、最具品牌价值、也是经营最为长久的连锁零售商一，沃尔玛多年深耕零售所积累的渠道影响力和消费者信任，...
					<text class="text24 colFA6C2F ml20">
						展开
					</text>
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
			back() {
				console.log('返回')
				uni.navigateBack()
			},

		}
	}
</script>

<style>
</style>