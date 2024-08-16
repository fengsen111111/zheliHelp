<template>
	<view>
		<view class="card text-center grid grid-cols-4">
			<view class="text-center" v-for="item in dataList" :key="item.id">
				<image :src="require('@/static/home/'+item.icon)" mode="" class="imgsIcon"></image>
				<view class="text20 col666666 line20 mb10">{{item.text}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				dataList: [
					{
						id:1,
						text:'饮料类',
						icon:'tag_a.png'
					},
					{
						id:2,
						text:'生疏类',
						icon:'tag_b.png'
					},
					{
						id:3,
						text:'粮油类',
						icon:'tag_c.png'
					},
					{
						id:4,
						text:'米面类',
						icon:'tag_d.png'
					},
					{
						id:5,
						text:'方便食品',
						icon:'tag_e.png'
					},
					{
						id:6,
						text:'生活用品',
						icon:'tag_f.png'
					},
					{
						id:7,
						text:'办公用品',
						icon:'tag_g.png'
					},
					{
						id:8,
						text:'更多',
						icon:'tag_h.png'
					}
				]
			}
		}
	}
</script>

<style>
	.imgsIcon{
		width: 96rpx;
		height: 96rpx;
		border-radius: 50%;
	}
</style>