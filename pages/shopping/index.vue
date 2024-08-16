<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="购物车" color="#000000" @clickLeft="back" />
		</view>
		<view class="bgF4F6F5 p30">
			<view class="grid grid-cols-2 text-center">
				<view class="text32">
				<view class="">商品</view>
				 <view class="border-bottom mx-auto"></view>
				</view>
				<view class="text28 col999999">团购</view>
			</view>
			<!--  -->
			<view class="card p30 flex items-center mt30 " v-for="item in [1,2,3,4]" :key="item">
				<view class=""><uni-icons type="checkbox-filled" size="26" color="#FA6C2F"></uni-icons></view>
				<view class="flex ml20">
					<image src="https://imgos.cn/2024/08/16/66bea893084a3.png" class="img170" mode=""></image>
					<view class="ml20 w370">
						<view class="text24 font-bold">
							面包糠1kg大包装面包屑炸鸡粉炸鸡裹 鸡排面包康
						</view>
						<view class="bgF4F6F5 text20 p10 text-center flex mt30 w180">
							<text>袋装(500g)*2</text>
							<uni-icons type="down" size="16" class="ml20" color="#FA6C2F"></uni-icons>
						</view>
						<view class="mt30 flex justify-between items-center text28 col-black">
							<view class="flex">
								<view class="">单价</view>
								<view class="colFF0000">￥6666</view>
							</view>
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
		<!-- 底部导航栏 -->
		<view class="w-full fixed bottom0">
			<view class="bg-white p30 flex text20 justify-between ">
				<view class="flex justify-between w-full items-center">
					<view class="colFA6C2F">
						全选
					</view>
					<view class="ml20 w-1-2"> 
						<view class="flex justify-between">
							<view class="col-black text30">
								结算金额
							</view>
							<view class="colFF0000 text30">
							   ￥6666
							</view>
						</view>
						<view class="col666666 flex justify-between" >
							<view class="">下单获得爱心值</view>
							<view class="">8888</view>
						</view>
					</view>
					<view class="ml30 bgFA6C2F w200 py22 text-center col-white text28 radius10">
						提交
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
				
			}
		},
		methods: {

		}
	}
</script>

<style>
	.border-bottom{
		background: linear-gradient( 90deg, #FB6E19 0%, #EA0306 100%);
		width: 96rpx;
		height: 8rpx;
		border-radius: 10rpx;
		margin-top: 7rpx;
	}
	
</style>
