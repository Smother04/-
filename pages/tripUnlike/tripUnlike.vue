<template>
	<view class="bgf7 page pd30 pdt20">
		<view class="flex flex-colum flex-between mrb20 bdrd14 bgfff" style="height: 670rpx;"
			v-for="(item,index) in tripUnlikeList" :key="index">
			<image style="width: 690rpx;height: 408rpx;" src="../../static/tripUnlike/514.png" mode="">
			</image>
			<view class="flex flex-colum flex1 flex-around mr14 ">
				<view class="font30 fontw500">
					<text class="">{{item.title}}</text>
				</view>
				<view class="font24 col555">
					<text>跟团游·可以拍照·2~3天</text>
				</view>
				<view class="flex">
					<view class="font24 bdrd8 flex flex-center align-center mrr14"
						style="width: fit-content;height: 40rpx;border: 2px solid #E89F2B;"
						v-for="(obj,i) in tagList" :key="i">
						<text class="mr10" style="color: #E89F2B;">{{obj.tag}}</text>
					</view>
				</view>
				<view class="font24 flex flex-between" style="color: #F94D29;">
					<view>
						<text>￥</text>
						<text class="font40">{{item.price.toFixed(2)}}</text>
						<text class="col888 ml14"
							style="text-decoration: line-through;">￥{{item.originPrice}}</text>
					</view>
					<view class="flex flex-center align-center bdrd40" style="width: 154rpx;height: 58rpx;background: #FEDC3F;">
						<text class="font28 col222">立即抢购</text>
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
				tripUnlikeList: [
					{
						title: '最美不过油菜花，亲子互动，体验自然的美好',
						price: 259,
						originPrice: 600
					},{
						title: '最美不过油菜花，亲子互动，体验自然的美好',
						price: 259,
						originPrice: 600
					},{
						title: '最美不过油菜花，亲子互动，体验自然的美好',
						price: 259,
						originPrice: 600
					},{
						title: '最美不过油菜花，亲子互动，体验自然的美好',
						price: 259,
						originPrice: 600
					},{
						title: '最美不过油菜花，亲子互动，体验自然的美好',
						price: 259,
						originPrice: 600
					},
				],
				tagList: [
					{
						tag: '过期退'
					},
					{
						tag: '未预约随时退'
					},
				]
			};
		}
	}
</script>

<style lang="scss">

</style>
