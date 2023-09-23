<template>
	<view class="bgcolor page">
		<image class="absolute w100" style="z-index: -1;height: 524rpx;" src="../../static/meetroom/528.png"
			mode="">
		</image>
		<scroll-view :scroll-y="true" class="" style="height: 100vh;">
			<view class=" absolute  clear w100" style="z-index: 10;">

				<view class="flex flex-colum align-center ">
					<image class="mrt32" style="width: 358rpx;height: 70rpx;" src="../../static/meetroom/组 6255@2x.png"
						mode="">
					</image>
					<text class="font28 mrt20 colfff">"文案文案文案文案文案文案文案"</text>
				</view>
				<scroll-view class="mt50 scrolView w100" style="white-space: nowrap; " scroll-x="true">
					<view class="scrolItem colfff" style="display: inline-block;"
						:class="current == index ? 'actived' : ''" @click="changeActive(index)"
						v-for="(item,index) in 12" :key="index">分类</view>
				</scroll-view>

				<view class=" bgfff mr30 mrt30 " v-for="item in activeList" :key="item">
					<view class="flex flex-between align-center pdx14 border-box" v-for="(item,index) in 8" :key="index"
						style="height: 280rpx;">
						<image style="width: 240rpx;height: 240rpx;" src="../../static/meetroom/225.png" mode="">
						</image>
						<view class=" flex1 flex flex-colum flex-between ml20" style="height: 240rpx;">
							<view class=" flex flex-colum">
								<view class="font30 fontw500">
									<text>武功山2023年，徒步华东户外 圣地，邂逅绝美风景</text>
								</view>
								<view class="font24 mrt10">
									<text>跟团游·徒步登山·2~3天</text>
								</view>
								<view class="mrt14 font24 flex flex-center align-center bdrd8"
									style="width: 116rpx;height: 40rpx; border: 2px solid #E89F2B;">
									<text class="font24">日出云海</text>
								</view>
							</view>
							<view class="flex flex-between mrt8">
								<view class="font40" style="color: #F94D29;">
									<text class="font24">￥</text>
									<text class="">259.00</text>
								</view>
								<view class="font24 col888  flex flexDCR ">
									<text class="">已售1000</text>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>


		</scroll-view>
	</view>


</template>

<script>
	export default {
		data() {
			return {
				current: 0,
				itemList: [],
				activeList: []
			};
		},
		onLoad() {
			for (let i = 0; i < 12; i++) {
				this.itemList.push([{
					text: i
				}])
			}
			this.activeList = this.itemList[0]
		},
		methods: {
			changeActive(index) {
				this.current = index
				this.activeList = this.itemList[index]
			}
		}
	}
</script>

<style lang="scss">
	.bgcolor {
		width: 750rpx;
		background: #015BA5;
		opacity: 1;
		position: absolute;
		z-index: -2;

		.bgBox {
			width: 750rpx;
			height: 524rpx;

			.topbox {
				display: flex;
				flex-direction: column;
				align-items: center;
				width: 448rpx;
				height: 118rpx;
				margin: 0 auto;
				padding-top: 30rpx;
			}
		}

		.scrolView {
			width: 100%;
			white-space: nowrap;
			margin-left: 30rpx;

			.scrolItem {
				display: inline-block;
				width: 148rpx;
				height: 70rpx;
				border-radius: 34rpx;
				text-align: center;
				line-height: 70rpx;
			}

			.actived {
				background: linear-gradient(90deg, #FFDF4B 0%, #EFC600 100%);
			}
		}
	}
</style>