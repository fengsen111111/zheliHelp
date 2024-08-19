<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="礼品卡详情" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="p30 bg-white mt20">
			<image src="https://imgos.cn/2024/08/16/66beaca2d4950.png" class="w-full h206" mode=""></image>
			<view class="text30 font-bold px30">
				陈昌银磁器口陈麻花重庆八绝520g特产礼盒
			</view>
			<view class="col999999 line32 text24 px30">
				百草味藕片+百草味蟹黄蚕豆+脆升升薯条+纳宝帝丽巧克威化饼干+可比克+娃哈哈AD钙奶+阿尔卑斯葡萄糖果+喜之郎果冻+旺仔牛奶糖+咪咪虾条+阿婆家的薯片+炭烤肉脯+旺旺开心馒头仔+开心浪味仙花式薯卷+琅琅脆蔬菜卷+手指尖三角酥+香辣味烤脖+散称鸭翅花花肠子大西北烤面筋散称豆你嗨皮+火锅素毛肚散称素牛排
			</view>
		</view>

		<view class="py20 px30 bg-white mt20">
			<view class="text30 font-bold">
				商品列表
			</view>
			<view class="px20 flex items-center justify-between mt30" v-for="item in [1,2,3,4,5]" :key="item">
				<image src="https://img.picui.cn/free/2024/08/16/66bf089662182.png" class="w100 h100 radius12" mode="">
				</image>
				<view class="text24 font-bold ml20">
					<view class=""> 陈昌银重庆磁器口精品豪华陈麻花百草味藕片零食</view>
					<view class="col999999"> 袋装(500g)</view>
				</view>
				<view class="col333333 ml20">
					X666
				</view>
			</view>
		</view>
		<!-- 固定 -->
		<view class="fixed bg-white bottom0 py30 w-full" style="position: fixed;">
			<view class="px75 text-center">
				<view class="text-center bgFA6C2F col-white py14 font-bold radius12" @click="toggle('bottom')">
					兑换
				</view>
				<view class="colFF0000 text24 ">
					该礼品卡不在兑换时间内
				</view>
			</view>
		</view>
		<!-- 兑换弹框 -->
		<uni-popup ref="popup" background-color="#fff" borderRadius="20rpx 20rpx 0px 0px">
			<view class="radius20 bg-white p30" style="height: 40vh;">
				<view class="flex justify-between items-center">
					<view class="w28"></view>
					<view class="">确认兑换</view>
					<view>
						<uni-icons type="closeempty" size="20" color="#666666" @click="cancel"></uni-icons>
					</view>
				</view>
				<!--  -->
				<view class="text24 mt20">
					<view class="flex items-center justify-between">
						<view class="">兑换码</view>
						<view class="text20 colFF0000">兑换码错误</view>
					</view>
					<view class="bgF4F6F5 p15 radius10 text24 mt20">
						<input type="text" placeholder="输入兑换码" />
					</view>
				</view>
				<view class="text24 mt20">
					<view class="flex items-center justify-between">
						<view class="">卡密密码</view>
						<view class="text20 colFF0000">卡密密码错误</view>
					</view>
					<view class="bgF4F6F5 p15 radius10 text24 mt20">
						<input type="text" placeholder="输入卡密密码" />
					</view>
				</view>
				
				<view class="bgFA6C2F radius12 py22 text28 font-bold mt50 col-white text-center" @click="handleGifrOder">
					支付
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {
			// 
			toggle(type) {
				this.type = type
				this.$refs.popup.open(type)
			},
			cancel() {
				this.$refs.popup.close()
			},
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleGifrOder(){
				uni.navigateTo({
					url:'/pages/childPages/gifrSubmitOder/index'
				})
			}
		}
	}
</script>

<style>
</style>