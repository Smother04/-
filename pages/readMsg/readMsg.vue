<template>
	<view class="page bgf7 px30">
		<view class="" v-for="(item,index) in msgList" :key="index">
			<view class="flex flex-center pdt30 pdb28">
				<view class="font24 col666 flex flex-between align-center" style="width: 188rpx;height: 24rpx;">
					<text>2023-9-23</text>
					<text>10:26</text>
				</view>
			</view>
			<view class="bgfff flex flex-colum flex-around pdl20 pdy40 border-box" style="width: 690rpx;height: 302rpx;">
				<view class="font30 col333 fontw400">
					<text>发货成功</text>
				</view>
				<view class="bgf8 flex flex-between" style="width: 651rpx;height: 152rpx;">
					<image style="width: 152rpx;height: 152rpx;" src="../../static/msg/3.png" mode=""></image>
					<view class="flex1 font28 col222 mrt30 mrl22 pdr40 border-box">
						<text>蒙牛纯甄 常温风味酸牛奶 中秋 送礼推荐 发货成功! </text>
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
				msgList: [
					{},
					{},
					{},
					{},
				]
			};
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>

</style>