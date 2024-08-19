<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="采集登记" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<image src="https://img.picui.cn/free/2024/08/19/66c2e39d1c2d0.png" class="w-full h328" mode=""></image>
		<!--  -->
		<view class="py20 px30 bg-white">
			<view class="text30 col333333">单位名称</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写单位名称" />
			</view>
			<view class="text30 col333333 mt30">采购员</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写采购员姓名" />
			</view>
			<view class="text30 col333333 mt30">采购员手机号</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写采购员手机号" />
			</view>
			<view class="text30 col333333 mt30">采购产品类型</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写采购产品类型" />
			</view>
			<view class="text30 col333333 mt30">采购总金额</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写采购总金额" />
			</view>
			<view class="text30 col333333 mt30">采购数量</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写采购数量" />
			</view>
			<view class="text30 col333333 mt30">采购详细</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<textarea type="text" placeholder="填写采购详细" class="h206"/>
			</view>
			<view class="flex justify-between items-center w-full mt20">
				<view class="flex items-center">
					<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
					<text class="text24 col999999 ml10">同意</text>
					<text class="text24 col36A9FC" @click="handleText">《采购协议》</text>
				</view>
				<view class="text20 colFF0000">
					未勾选同意采购协议
				</view>
			</view>
			<view class="w-full bgFA6C2F col-white text-center py14 font-bold text28 radius12 mt40" @click="centerPay('center')">
				提交
			</view>
		</view>
		<!-- 提交结果 -->
		<view class="">
			<uni-popup ref="popupCenter" background-color="#fff" borderRadius="20rpx 20rpx 20rpx 20rpx">
				<view class="radius20 bg-white p30" style="width: 70vw;">
					<view class="flex justify-between items-center">
						<view class="w28"></view>
						<view class="">提交失败/成功</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancelCenterPay"></uni-icons>
						</view>
					</view>
					<view class="text-center mt30">
						<image src="@/static/home/payCancel.png" class="w70 h70" mode=""></image>
						<image src="@/static/home/payOk.png" class="w70 h70" mode=""></image>
						<view class="mt15 col666666 text24">
							表单已提交
						</view>
					</view>
					
					<!--  -->
					<view class="bg36A9FC text28 text-center py22 w-full col-white  radius50 mt50" @click="cancelCenterPay">
						返回
					</view>
				</view>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {
			handleText(){
				uni.navigateTo({
					url:'/pages/childPages/contentView/index'
				})
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
            // 结果弹框
			centerPay(type) {
				// 打开新弹框
				this.type = type
				this.$refs.popupCenter.open(type)
			},
			cancelCenterPay() {
				this.$refs.popupCenter.close()
			},
		}
	}
</script>

<style>
</style>