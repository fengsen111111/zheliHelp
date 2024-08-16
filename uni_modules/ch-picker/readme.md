
## 基本用法
```html
<template>
	<view class="content">
		<button type="default" @tap="pickerShow">点击显示{{JSON.stringify(curIndexs)}}</button>
		<ch-picker ref="ChPicker" position="bottom" :columns="columns" :defaultIndex="curIndexs" @change="pickerChange">
		</ch-picker>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				curIndexs: [2, 1, 1],
				columns: [
					[{label: 0,value: 0,},{label: 1,value: 1,},{label: 2,value: 2,},{label: 3,value: 3,},],
					[{label: 0,value: 0,},{label: 1,value: 1,},{label: 2,value: 2,},{label: 3,value: 3,},],
					[{label: 0,value: 0,},{label: 1,value: 1,},{label: 2,value: 2,},{label: 3,value: 3,},]
				],
			}
		},
		onLoad() {},
		methods: {
			pickerShow() {
				this.$refs.ChPicker.show()
			},
			pickerChange(e) {
				// console.log(e);
				this.curIndexs = e.indexs
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
```
			
## 启动方式
	`this.$refs.ChPicker.show()`

## 属性
| 属性 | 描述 | 类型 | 默认值 |
|--|--|--|--|
| clickMaskClose| 点击遮罩层关闭 | Boolean | true |
| columns| 每一列的数据 | Array| [] |
| defaultIndex| 默认选中值的下标，是数组 | Array | [] |
| position| 悬浮位置 | String | bottom |
| visibleCount| 每列中可见选项的数量，最大为5,最小为3 | String, Number | 5 |
| width| position为center时生效，不含单位时，默认单位是px | String, Number | 60vw |
| itemHeight| 单个选项的高度，会覆盖itemStyle内的height，单位是px | String, Number | 44 |
| itemStyle| 单个选项样式 | Object | {} |
| fields| 数组属性 | Object | {label: 'label',value: 'value',} |

## 事件
| 属性 | 描述 | 回调参数
|--|--|--|--|
| change| 实时监听，选项发生改变时触发 | {indexs, columns}，indexs：选中项下标数组；columns：选中项数组 |
| confirm| 点击确认按钮触发 | {indexs, columns}，indexs：选中项下标数组；columns：选中项数组 |
| cancel| 点击取消按钮触发 | - |
