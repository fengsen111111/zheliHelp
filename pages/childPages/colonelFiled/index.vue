<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="团长管理" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30 bg-white mt20">
			<view class="text30 col333333">姓名</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写姓名" />
			</view>
			<view class="text30 col333333 mt30">电话</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写电话" />
			</view>
			<view class="text30 col333333 mt30">身份证号</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写身份证号" />
			</view>
			<view class="text30 col333333 mt30">地址</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写地址" />
			</view>
			<view class="text30 col333333 mt30">自提点名称</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写自提点名称" />
			</view>
			<view class="text30 col333333 mt30">自提点照片</view>
			<view class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				自提点照片
			</view>
		</view>
		<!-- 底部固定 -->
		<view class="fixed bottom0 w-full bg-white">
			<view class="py30 px75">
				<view class="bg36A9FC col-white text28 font-bold text-center py14 radius12" @click="handleGo">
					已经提交过了，跳转
				</view>
				<view class="bg36A9FC col-white text28 font-bold text-center py14 radius12" @click="centerPay('center')">
					提交
				</view>
				
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
						确定
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
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleGo(){
				uni.navigateTo({
					url:'/pages/childPages/colonel/index'
				})
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