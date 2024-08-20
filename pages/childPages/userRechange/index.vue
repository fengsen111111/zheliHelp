<template>
	<view class="bgF4F6F5">
		<view class="">
			<uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left"
				title="会员充值" color="#000000" @clickLeft="back" />
		</view>
		<!--  -->
		<view class="py20 px30 mt20 bg-white">
			<view class="text30 font-bold">充值</view>
			<view class="flex justify-around col333333 mt20">
				<view class="flex" @click="handleIndex(1)">
					<uni-icons type="checkbox" color="#FA6C2F" size="20" v-if="selIndex ==1"></uni-icons>
					<uni-icons type="circle" size="20" v-else></uni-icons>
					<view class="text28">当前账号</view>
				</view>
				<view class="flex" @click="handleIndex(2)">
					<uni-icons type="checkbox" color="#FA6C2F" size="20" v-if="selIndex ==2"></uni-icons>
					<uni-icons type="circle" size="20" v-else></uni-icons>
					<view class="text28">他人充值</view>
				</view>
			</view>
			<view v-if="selIndex ==2" class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写充值手机号" />
			</view>
		</view>
		<!--  -->
		<view class="py20 px30 mt20 bg-white">
			<view class="text30 font-bold">充值金额</view>
			<view class="flex justify-between col333333 mt20">
				<view @click="handleView(1)" :class="viewIndex==1?'text24 colFA6C2F borderFA6C2F':''" class="py30 px20 col999999 bgF4F6F5 radius12 font-bold">
					100元
				</view>
				<view @click="handleView(2)" :class="viewIndex==2?'text24 colFA6C2F borderFA6C2F':''" class="py30 px20 col999999 bgF4F6F5 radius12 font-bold">
					200元
				</view>
				<view @click="handleView(3)" :class="viewIndex==3?'text24 colFA6C2F borderFA6C2F':''" class="py30 px20 col999999 bgF4F6F5 radius12 font-bold">
					300元
				</view>
				<view @click="handleView(4)" :class="viewIndex==4?'text24 colFA6C2F borderFA6C2F':''" class="py30 px20 col999999 bgF4F6F5 radius12 font-bold" >
				    其他数量
				</view>
			</view>
			<view v-if="viewIndex ==4" class="bgF4F6F5 radius10 px20 mt20 col999999 py14">
				<input type="text" placeholder="填写充值金额" />
			</view>
		</view>
		<!-- 固定 -->
		<view class="fixed bottom0 bg-white w-full py14">
			 <view class="flex items-center justify-between">
			 	<view class="text30 ml30">总计</view>
				<view class="flex items-center mr30">
					<view class="colFF0000 font-bold text40">
						￥6666
					</view>
					<view class="ml40 py22 px75 bgFA6C2F radius12 col-white text-center text28 font-bold"> 
						支付
					</view>
				</view>
			 </view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				selIndex:1,
				viewIndex: 4
			}
		},
		methods: {
			back() {
				console.log('返回')
				uni.navigateBack()
			},
			handleIndex(index) {
				this.selIndex = index
			},
			handleView(index){
				this.viewIndex = index
			}

		}
	}
</script>

<style>
</style>