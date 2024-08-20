<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="礼品卡启用" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30 bg-white mt20">
			<view class="font-bold text30 ">启用礼品卡</view>
			<view class="flex items-center mt20 justify-between">
				<view class="bgF4F6F5 px20 py10 w-7-10 radius12">
					<input type="text" placeholder="填写礼品卡卡号" class="text24" />
				</view>
				<view class="bgFA6C2F col-white text28 radius10 font-bold  py10 px40">
					激活
				</view>
			</view>
		</view>
		<!--  -->
		<view class="py20 px30 bg-white mt20">
			<view class="font-bold text30 ">激活记录</view>
			<view class="bgF4F6F5 mt20 text24 radius10 p20">
				<view class="flex justify-between items-center">
					<view class="flex">
						<text>卡名</text>
						<text class="ml10">礼品卡名称</text>
					</view>
					<view class="text-center">
						<uni-icons type="undo" size="20" color="#FF0000"></uni-icons>
						<view class="text20 colFF0000">
							撤销
						</view>
					</view>
				</view>
				<view class="flex">
					<text>卡号</text>
					<text class="ml10">XXXXXXXXXXXXXXXXX</text>
				</view>
				<view class="flex mt15">
					<text>激活时间</text>
					<text class="ml10">XXXX-XX-XX XX:XX</text>
				</view>
			</view>
			<view class="h206"></view>
			<view class="h206"></view>
			<view class="h206"></view>
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