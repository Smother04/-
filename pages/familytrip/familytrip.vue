<template>
	<view class="bgf7 flex flex-wrap flex-between mr30">
		<view class="flex flex-colum flex-between mrb20 bgfff" style="width: 336rpx;height: 566rpx;"
			v-for="(item,index) in tripList" :key="index">
			<image style="width: 336rpx;height: 336rpx;" src="../../static/home/sp20230914_150137_567.png" mode="">
			</image>
			<view class="flex flex-colum flex1 flex-around mr14 ">
				<view class="">
					<text class="font28 fontw500 col222">{{item.title}}</text>
				</view>
				<view class="font24 bdrd8 flex flex-center align-center"
					style="width: 116rpx;height: 40rpx;border: 2px solid #E89F2B;">
					<text style="color: #E89F2B;">户外徒步</text>
				</view>
				<view class="font24" style="color: #F94D29;">
					<text>￥</text>
					<text class="font40">{{item.price.toFixed(2)}}</text>
					<text class="col888 ml14"
						style="text-decoration: line-through;">￥{{item.originPrice.toFixed(2)}}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tripList: [{
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					}, {
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					},
					{
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					}, {
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					}, {
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					}, {
						title: '万科时代广场/万象城商业',
						price: 29.00,
						originPrice: 36.00
					},
				]
			};
		}
	}
</script>

<style lang="scss">

</style>