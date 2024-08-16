<template>
	<view class="">
		<view class="">
		  <uni-nav-bar :border="false" :fixed="true" background-color="#ffffff" status-bar left-icon="left" title="礼品卡" color="#000000" @clickLeft="back" />
		</view>
		<view class="bgF4F6F5 p30">
			<view class="card mb30" :class="item.id!==1?'':''" v-for="item in imgList" :key="item.id">
				<image :src="item.url" mode="" class="w-full h206"></image>
				<view class="font-bold col-black mt10 text30 px30">陈昌银磁器口陈麻花重庆八绝520g特产礼盒</view>
				<view class="col999999 text24 mt10 px30">百草味藕片+百草味蟹黄蚕豆+脆升升薯条+纳宝帝丽巧克+威化饼干+可比克+娃哈哈AD钙奶+阿尔卑斯葡萄糖...</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgList:[{
					id: '1',
					url:'https://imgos.cn/2024/08/16/66beaca2d4950.png'
				},
				{
					id: '2',
					url:'https://imgos.cn/2024/08/16/66beaca2dd1fb.png'
				},
				{
					id: '3',
					url:'https://imgos.cn/2024/08/16/66beaca30ea62.png'
				}
				]
			}
		},
		methods: {

		}
	}
</script>

<style>
	
</style>
