<template>
	<view class="bgf7 vh100">
		<view class="minebg"></view>

		<view class="TopBox">
			<view class="flex flex-between w100">
				<view class="leftbox">
					<view class="imgbox">
						<image class="image" src="../../static/home/sp20230914_150137_567.png" mode=""></image>
					</view>
					<view class="messagebox">
						<view>
							<text class="font36 col222 username">GJZ</text>
							<view class="font24 colfff tel bd">
								135******00
							</view>
						</view>
					</view>
				</view>
				<view class="rightbox">
					<view class="flex flex-between">
						<image class="sign" @click="signChange()" src="../../static/mine/sp20230918_103948_291.png" mode=""></image>
						<image class="info" @click="readMsg()" src="../../static/mine/组 5304@2x.png" mode=""></image>
					</view>
				</view>
			</view>
			<view class="flex flex-around w100">
				<view class="flex flex-colum align-center">
					<text class="font40 fontw500 col222">1</text>
					<text class="font28 fontw400 col222">我的推广</text>
				</view>
				<view class="flex flex-colum align-center">
					<text class="font40 fontw500 col222">2</text>
					<text class="font28 fontw400 col222">我的种草</text>
				</view>
				<view class="flex flex-colum align-center">
					<text class="font40 fontw500 col222">3</text>
					<text class="font28 fontw400 col222">我的积分</text>
				</view>
			</view>
			<view class="menubox bgfff">
				<view class="item" v-for="(item,index) in menuList" :key="index">
					<image class="icon" :src="item.icon" mode=""></image>
					<text class="font28">{{item.label}}</text>
				</view>
			</view>
		</view>

		<view class="BottonBox">
			<view class="infobox bgfff" v-for="(item,index) in list" :key="index">
				<view class="leftInfo">
					<image style="width: 40rpx;height: 40rpx;" :src="item.img" mode=""></image>
					<text>{{item.title}}</text>
				</view>
				<image style="width: 8rpx;height: 16rpx;padding-right: 30rpx;" src="../../static/mine/路径 4083.png" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menuList: [{
					icon: "../../static/mine/组 6161.png",
					label: "待付款"
				}, {
					icon: "../../static/mine/组 6162.png",
					label: "待使用"
				}, {
					icon: "../../static/mine/sp20230918_125021_088.png",
					label: "待评价"
				}, {
					icon: "../../static/mine/组 6164.png",
					label: "售后单"
				}, {
					icon: "../../static/mine/组 6165.png",
					label: "全部订单"
				}, ],
				list: [{
					img: "../../static/mine/组 6266.png",
					title: "商品收藏"
				}, {
					img: "../../static/mine/sp20230918_155923_078.png",
					title: "我的佣金"
				}, {
					img: "../../static/mine/sp20230918_160310_309.png",
					title: "门店入住"
				}, {
					img: "../../static/mine/sp20230918_160353_525.png",
					title: "我的客服"
				}, {
					img: "../../static/mine/sp20230918_160432_492.png",
					title: "关于我们"
				}]
			}
		},
		methods: {
			// 跳转到消息通知页面
			readMsg(){
				uni.navigateTo({
					url: '/pages/readMsg/readMsg'
				})
			},
			// 跳转到签到页面
			signChange(){
				uni.navigateTo({
					url: '/pages/credits/credits'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.minebg {
		position: absolute;
		width: 100%;
		height: 392rpx;
		background: #FFD719;
		z-index: 1;
		top: 0;
	}

	.TopBox {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		position: relative;
		width: 690rpx;
		height: 498rpx;
		z-index: 2;
		padding-left: 26rpx;
		padding-right: 26rpx;

		.leftbox {
			width: 306rpx;
			height: 128rpx;
			display: flex;
			justify-content: space-between;

			.imgbox {
				width: 128rpx;
				height: 128rpx;
				border: 1px solid #F3F2F2;
				border-radius: 50%;

				.image {
					width: 116rpx;
					height: 116rpx;
					margin: 6rpx;
					border-radius: 50%;
				}
			}

			.messagebox {
				width: 162rpx;
				display: flex;
				align-items: center;

				.username {
					font-weight: normal;
				}

				.tel {
					width: 162rpx;
					height: 44rpx;
					background: #000000;
					border-radius: 42rpx;
					line-height: 42rpx;
					text-align: center;
					margin-top: 22rpx;
					opacity: 0.5;
				}
			}
		}

		.rightbox {
			width: 80rpx;

			.sign {
				width: 29rpx;
				height: 28rpx;
			}

			.info {
				width: 26rpx;
				height: 28rpx;
			}
		}

		.menubox {
			width: 100%;
			height: 186rpx;
			display: flex;
			justify-content: space-around;
			align-items: center;
			border-radius: 14rpx;

			.item {
				width: 112rpx;
				height: 110rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-around;
				align-items: center;

				.icon {
					width: 56rpx;
					height: 56rpx;
				}
			}
		}
	}

	.BottonBox {
		padding-left: 26rpx;
		padding-right: 26rpx;
		margin-top: 24rpx;
		.infobox {
			width: 690rpx;
			height: 100rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			border-radius: 14rpx;
			margin-bottom: 20rpx;

			.leftInfo {
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding-left: 30rpx;
				width: 176rpx;
				height: 100rpx;
			}
		}
	}
</style>