<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="提交订单" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
	    <view class="bg-white py14 px30 flex justify-between">
	    	<view class="flex items-center">
	    		<view class="text24 col-black font-bold">员工自提卡</view>
				<view class="colFF0000 text20 ml20">单位员工卡可在此处下单刷卡自提</view>
	    	</view>
			<uni-icons type="right" size="20" color="#FA6C2F"></uni-icons>
	    </view>
		<!-- 自提点 -->
		<view class="">
			<!--  -->
			<view class="bg-white px30 py20 mt30">
				<view class="col333333 w-full justify-between text30 flex items-center">
					<view class="flex items-center">
						<view class="">选择自提点</view>
						<view class="colFF0000 text20">单位员工卡可在此处下单刷卡自提</view>
					</view>
					<view class="colFA6C2F text20" @click="handleReplace">更换</view>
				</view>
				<view class="flex items-center col333333 mt36 justify-between">
					<view class="ml20">
						<image src="https://img.picui.cn/free/2024/08/19/66c2ab85a4a4d.png" class="w120 h120 radius12"
							mode=""></image>
					</view>
					<view class="ml20">
						<view class="text24">沃尔玛超市</view>
						<view class="text20 col999999">联系人：张三 12312341234</view>
						<view class="text20 col999999">四川省成都市武侯区桂溪街道桂溪街道世纪城南路67号</view>
					</view>
					<view class="text-center mr20">
						<uni-icons type="location" size="20"></uni-icons>
						<view class="col999999 text20">
							888km
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 送货上门 -->
		<view class="">
			<view class="bg-white px30 py20 mt30">
				<view class="col333333 w-full justify-between text30 flex items-center">
					<view class="flex items-center">
						<view class="">收货地址</view>
					</view>
					<view class="colFA6C2F text20" @click="toggle('bottom')">更换</view>
				</view>
				<view class="px20">
					<view class="mt20  flex text24 col333333">
						<view class="">张三</view>
						<view class="">12312341234</view>
					</view>
					<view class="col333333 mt10 flex items-center justify-between">
						<view class="text24">成都市高新区世纪城天府大道中段588号</view>
						<view class="colFF0000 text20">超出配送范围</view>
					</view>
				</view>
			</view>
		</view>
		<!--  -->
		<view class="bg-white px30 py20 mt30">
			<view class="col333333 text30">
				联系方式
			</view>
			<view class="bgF4F6F5 p15 radius10 text24 mt20">
				<input type="text" placeholder="填写联系人姓名" />
			</view>
			<view class="bgF4F6F5 p15 radius10 text24 mt20">
				<input type="text" placeholder="填写联系手机号" />
			</view>
		</view>
		<!--  -->
		<view class="bg-white items-center justify-between px40 py20 mt30 flex">
			<view class="flex">
				<view class="">
					<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w170 h170 radius12"
						mode=""></image>
				</view>
				<view class="ml20">
					<view class="text24 col333333 font-bold">面包糠1kg大包装面包屑炸鸡粉炸鸡裹 鸡排面包康</view>
					<view class="bgF4F6F5 text-center flex text20 w200 mt10" >
						<view>袋装(500g)*2</view>
						<uni-icons type="down" color="#FA6C2F" class="ml10" size="20"></uni-icons>
					</view>
					<view class="flex justify-between">
						<view class="flex mt10 items-center text28  text-center">
							<view class=" col333333 font-bold">单价</view>
							<view class=" colFF0000  font-bold">￥6666</view>
						</view>
						<view class="">
							<view class="bgF4F6F5 text28 items-center flex ml30">
								<image src="@/static/shopping/dowm.png" class="img50" mode=""></image>
								<view class="px8 py5">
									9999
								</view>
								<image src="@/static/shopping/add.png" class="img50" mode=""></image>
							</view>
						</view>
					</view>
				</view>
			</view>
			
		</view>
		<!--  -->
		<view class="bg-white px30 py20 mt30">
			<view class="col333333 text30">
				备注（选填）
			</view>
			<view class="bgF4F6F5 p15 radius10 text24 mt20">
				<textarea type="text" placeholder="填写备注" />
			</view>
		</view>
		<!-- 固定 -->
		<view class="">
			<view class="flex w-full py14 items-center justify-between fixed bottom0 bg-white">
				<view class="ml30 w520">
					<view class="flex justify-between text30">
						<view class="">结算金额</view>
						<view class="flex text20 col666666">
							<view class="">运费</view>
							<view class="colFF0000">+￥66</view>
						</view>
						<view class="colFF0000">￥6666</view>
					</view>
				
					<view class="flex justify-between text20 col666666">
						<view class="">下单获得爱心值</view>
						<view class="">￥8888</view>
					</view>
				</view>
				<view class="mr30 bgFA6C2F col-white radius12 py20 px40 text-center" @click="togglePay('bottom')">
					提交
				</view>
			</view>
		</view>
		<!-- 地址切换弹框 -->
		<view>
			<uni-popup ref="popup" background-color="#fff" borderRadius="20rpx 20rpx 0px 0px">
				<view class="radius20 bg-white p30" style="height: 30vh;">
					<view class="flex justify-between items-center">
						<view class="colFA6C2F text20">管理地址</view>
						<view class="">地址选择</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancel"></uni-icons>
						</view>
					</view>
					<!--  -->
					<view class="bgF4F6F5 p20 flex items-center justify-between mt20" v-for="item in [1,2,3]"
						:key="item">
						<view class=" text24 col333333">
							<view class="">张三 12312341234</view>
							<view class="">成都市高新区世纪城天府大道中段588号</view>
						</view>
						<view class="" v-if="item ==1">
							<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
						</view>

					</view>
				</view>
			</uni-popup>
		</view>
		<!-- 支付方式 -->
		<view>
			<uni-popup ref="pay" background-color="#fff" borderRadius="20rpx 20rpx 0px 0px">
				<view class="radius20 bg-white p30" style="height: 45vh;">
					<view class="flex justify-between items-center">
						<view class="w28"></view>
						<view class="">支付方式</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancelPay"></uni-icons>
						</view>
					</view>
					<!--  -->
					<view class=" p20 flex items-center justify-between mt20" @click="handlePayIndex(1)">
						<view class="flex items-center">
							<image src="@/static/home/pay1.png" class="w40 h32" mode=""></image>
							<view class="text30 font-bold ml20">微信</view>
						</view>
						<view class="" v-if="payIndex==1">
							<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
						</view>
					</view>
					<view class=" p20 flex items-center justify-between mt20" @click="handlePayIndex(2)">
						<view class="flex items-center">
							<image src="@/static/home/pay2.png" class="w40 h32" mode=""></image>
							<view class="text30 font-bold ml20">会员卡</view>
						</view>
						<view class="" v-if="payIndex==2">
							<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
						</view>
					</view>
					<view class=" p20 flex items-center justify-between mt20" @click="handlePayIndex(3)">
						<view class="flex items-center">
							<image src="@/static/home/pay3.png" class="w40 h40" mode=""></image>
							<view class="text30 font-bold ml20">员工卡</view>
						</view>
						<view class="" v-if="payIndex==3">
							<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
						</view>
					</view>
					<view class=" p20 flex items-center justify-between mt20" @click="handlePayIndex(4)">
						<view class="flex items-center">
							<image src="@/static/home/pay4.png" class="w40 h40" mode=""></image>
							<view class="text30 font-bold ml20">老人卡</view>
						</view>
						<view class="" v-if="payIndex==4">
							<uni-icons type="checkbox" color="#FA6C2F" size="20"></uni-icons>
						</view>
					</view>
					<!--  -->
					<view class="bgFA6C2F text28 text-center py22 w-full col-white  radius12 mt50"
						@click="toggleOkPay('bottom')">
						立即支付
					</view>
				</view>
			</uni-popup>
		</view>
		<!-- 确认支付 -->
		<view>
			<uni-popup ref="okPay" background-color="#fff" borderRadius="20rpx 20rpx 0px 0px">
				<view class="radius20 bg-white p30" style="height: 45vh;">
					<view class="flex justify-between items-center">
						<view class="w28"></view>
						<view class="">确认支付</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancelOkPay"></uni-icons>
						</view>
					</view>
					<!--  -->
					<view class="flex justify-between text24 p20">
						<view class="">
							支付密码
						</view>
						<view class="colC32519">
							密码不正确
						</view>
					</view>
					<view class="bgF4F6F5 radius10 col999999 text24 p20">
						<input type="text" placeholder="输入支付密码" />
					</view>
					<!--  -->
					<view class="bgFA6C2F text28 text-center py22 w-full col-white  radius12 mt50"
						@click="centerPay('center')">
						支付
					</view>
				</view>
			</uni-popup>
		</view>
		<!-- 支付结果 -->
		<view class="">
			<uni-popup ref="popupCenter" background-color="#fff" borderRadius="20rpx 20rpx 20rpx 20rpx">
				<view class="radius20 bg-white p30" style="width: 70vw;">
					<view class="flex justify-between items-center">
						<view class="w28"></view>
						<view class="">支付失败/成功</view>
						<view>
							<uni-icons type="closeempty" size="20" color="#666666" @click="cancelCenterPay"></uni-icons>
						</view>
					</view>
					<view class="text-center mt30">
						<image src="@/static/home/payCancel.png" class="w70 h70" mode=""></image>
						<image src="@/static/home/payOk.png" class="w70 h70" mode=""></image>
						<view class="mt15 col666666 text24">
							支付余额不足，请充值
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
			return {
				selIndex: 2,
				payIndex: 1
			}
		},
		methods: {
			handlePayIndex(index) {
				this.payIndex = index
			},
			handleIndex(index) {
				this.selIndex = index
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			// 更换个人地址
			toggle(type) {
				this.type = type
				this.$refs.popup.open(type)
			},
			cancel() {
				this.$refs.popup.close()
			},
			// 支付
			togglePay(type) {
				this.type = type
				this.$refs.pay.open(type)
			},
			cancelPay() {
				this.$refs.pay.close()
			},
			// 确认支付
			toggleOkPay(type) {
				this.type = type
				this.$refs.okPay.open(type)
			},
			cancelOkPay() {
				this.$refs.okPay.close()
			},
			// 支付结果弹框
			centerPay(type) {
				// 关闭其余弹框
				this.cancelOkPay() //确认支付
				this.cancelPay() //支付
				// 打开新弹框
				this.type = type
				this.$refs.popupCenter.open(type)
			},
			cancelCenterPay() {
				this.$refs.popupCenter.close()
			},
			handleReplace() {
				console.log('跟换自提点');
				uni.navigateTo({
					url: '/pages/childPages/pickUpPoint/index'
				})
			}
		}
	}
</script>

<style>
</style>