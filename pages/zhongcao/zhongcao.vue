<template>
	<view class="bgf7">
		<view class="fixed flex flex-center align-center publish mrr30" @click="goPublish()">
			<text class="font28">发布</text>
		</view>
		<view class="flex flex-colum">
			<u-sticky bgColor="#fff">
				<u-tabs :list="list" class="font30" @click="click" lineWidth="0"
					:activeStyle="{color: '#303133',fontWeight: 'bold',transform: 'scale(1.05)'}"
					:inactiveStyle="{color: '#606266',transform: 'scale(1)'}"
					itemStyle="padding-left: 30rpx; padding-right: 30rpx; height: 84rpx;">
					<view slot="right" @tap="$u.toast('插槽被点击')">
						<view class="flex flex-center align-center" style="width: 72rpx;height: 84rpx;">
							<u-icon name="arrow-down" size="44"></u-icon>
						</view>
					</view>
				</u-tabs>
			</u-sticky>
			<view v-show="current === 0" class="flex flex-between flex-wrap mr30 mrt16">
				<view class="flex flex-colum flex-between mrb20 bgfff" style="width: 336rpx;height: 542rpx;"
					v-for="(item,index) in scenicList" :key="index">
					<image style="width: 336rpx;height: 374rpx;" src="../../static/home/sp20230914_150137_567.png"
						mode=""></image>
					<view class="flex flex-colum flex-around mr14" style="height: 168rpx;width: 310rpx;">
						<text class="font28 fontw500 col222">{{item.title}}</text>
						<view class="flex flex-between">
							<view class="flex align-center">
								<image class="bdrd50" src="../../static/home/sp20230913_172329_178.png"
									style="width: 34rpx;height: 34rpx;"></image>
								<text class="font24 fontw400 col555 mrl10">{{item.name}}</text>
							</view>
							<view class="flex align-center">
								<image src="../../static/home/组 6420@2x.png" style="width: 22rpx;height: 20rpx;"
									mode=""></image>
								<text class="font24 fontw400 col555 mrl10">{{item.number}}</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view v-show="current === 1" class="flex flex-between flex-wrap mr30 mrt16">
				<view class="flex flex-colum flex-between bdrd20 mrb20 bgfff" style="width: 336rpx;height: 542rpx;"
					v-for="(item,index) in scenicList" :key="index">
					<image style="width: 336rpx;height: 374rpx;" src="../../static/classify/组 6310@2x.png" mode="">
					</image>
					<view class="flex flex-colum flex-around mr14" style="height: 168rpx;width: 310rpx;">
						<text class="font28 fontw500 col222">{{item.title}}</text>
						<view class="flex flex-between">
							<view class="flex align-center">
								<image class="bdrd50" src="../../static/home/sp20230913_172329_178.png"
									style="width: 34rpx;height: 34rpx;"></image>
								<text class="font24 fontw400 col555 mrl10">{{item.name}}</text>
							</view>
							<view class="flex align-center">
								<image src="../../static/home/组 6420@2x.png" style="width: 22rpx;height: 20rpx;"
									mode=""></image>
								<text class="font24 fontw400 col555 mrl10">{{item.number}}</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view v-show="current === 2" class="flex flex-between flex-wrap mr30 mrt16">
				<view class="flex flex-colum flex-between bdrd20 mrb20 bgfff" style="width: 336rpx;height: 542rpx;"
					v-for="(item,index) in scenicList" :key="index">
					<image style="width: 336rpx;height: 374rpx;" src="../../static/classify/组 6307@2x.png" mode="">
					</image>
					<view class="flex flex-colum flex-around mr14" style="height: 168rpx;width: 310rpx;">
						<text class="font28 fontw500 col222">{{item.title}}</text>
						<view class="flex flex-between">
							<view class="flex align-center">
								<image class="bdrd50" src="../../static/home/sp20230913_172329_178.png"
									style="width: 34rpx;height: 34rpx;"></image>
								<text class="font24 fontw400 col555 mrl10">{{item.name}}</text>
							</view>
							<view class="flex align-center">
								<image src="../../static/home/组 6420@2x.png" style="width: 22rpx;height: 20rpx;"
									mode=""></image>
								<text class="font24 fontw400 col555 mrl10">{{item.number}}</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view v-show="current === 3" class="flex flex-between flex-wrap mr30 mrt16">
				<view class="flex flex-colum flex-between bdrd20 mrb20 bgfff" style="width: 336rpx;height: 542rpx;"
					v-for="(item,index) in scenicList" :key="index">
					<image style="width: 336rpx;height: 374rpx;" src="../../static/home/sp20230914_085703_635.png"
						mode=""></image>
					<view class="flex flex-colum flex-around mr14" style="height: 168rpx;width: 310rpx;">
						<text class="font28 fontw500 col222">{{item.title}}</text>
						<view class="flex flex-between">
							<view class="flex align-center">
								<image class="bdrd50" src="../../static/home/sp20230913_172329_178.png"
									style="width: 34rpx;height: 34rpx;"></image>
								<text class="font24 fontw400 col555 mrl10">{{item.name}}</text>
							</view>
							<view class="flex align-center">
								<image src="../../static/home/组 6420@2x.png" style="width: 22rpx;height: 20rpx;"
									mode=""></image>
								<text class="font24 fontw400 col555 mrl10">{{item.number}}</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view v-show="current === 4" class="flex flex-between flex-wrap mr30 mrt16">
				<view class="flex flex-colum flex-between bdrd20 mrb20 bgfff" style="width: 336rpx;height: 542rpx;"
					v-for="(item,index) in scenicList" :key="index">
					<image style="width: 336rpx;height: 374rpx;" src="../../static/home/sp20230913_172329_178.png"
						mode=""></image>
					<view class="flex flex-colum flex-around mr14" style="height: 168rpx;width: 310rpx;">
						<text class="font28 fontw500 col222">{{item.title}}</text>
						<view class="flex flex-between">
							<view class="flex align-center">
								<image class="bdrd50" src="../../static/home/sp20230913_172329_178.png"
									style="width: 34rpx;height: 34rpx;"></image>
								<text class="font24 fontw400 col555 mrl10">{{item.name}}</text>
							</view>
							<view class="flex align-center">
								<image src="../../static/home/组 6420@2x.png" style="width: 22rpx;height: 20rpx;"
									mode=""></image>
								<text class="font24 fontw400 col555 mrl10">{{item.number}}</text>
							</view>
						</view>
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
				current: 0,
				list: [{
					name: '关注',
				}, {
					name: '推荐',
				}, {
					name: '电影'
				}, {
					name: '科技'
				}, {
					name: '音乐'
				}, {
					name: '美食'
				}, {
					name: '文化'
				}, {
					name: '财经'
				}, {
					name: '手工'
				}],
				scenicList: [{
					title: '江西旅游景点#上饶葛仙村~最近上饶葛仙山峦',
					img: '',
					name: '一城山水',
					number: 4588
				}, {
					title: '江西旅游景点#上饶葛仙村~最近上饶葛仙山峦',
					img: '',
					name: '一城山水',
					number: 4588
				}, {
					title: '江西旅游景点#上饶葛仙村~最近上饶葛仙山峦',
					img: '',
					name: '一城山水',
					number: 4588
				}, {
					title: '江西旅游景点#上饶葛仙村~最近上饶葛仙山峦',
					img: '',
					name: '一城山水',
					number: 4588
				}, {
					title: '江西旅游景点#上饶葛仙村~最近上饶葛仙山峦',
					img: '',
					name: '一城山水',
					number: 4588
				}, ]
			}
		},
		methods: {
			click(item) {
				console.log('item', item);
				this.current = item.index
			},
			goPublish(){
				uni.navigateTo({
					url: '/pages/publish/publish'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.publish {
		width: 80rpx;
		height: 80rpx;
		z-index: 10;
		right: 0;
		bottom: 5%;
		border-radius: 50%;
		background: linear-gradient(88deg, #FEDC3F 0%, #FFD719 100%);
	}
</style>