<template>
	<view class="">
		<view class="goodBox" v-if="goodList.length > 0">
			<view class="searchList" v-for="(item,i) in goodList" :key="i" @click="goodDetail()">
				<view class="goodContent">
					<view class="bgImg">
						<image src="../../static/classify/组 3980.png" mode=""></image>
					</view>
					<view class="goodsInfo">
						<text class="">防疫物品清单</text>
					</view>
					<view class="Tips">
						限时抢购热门新款
					</view>
				</view>
			</view>
		</view>
		<view class="noData" v-else>
			<image src="https://cphui.app65.cn/index_image/static/null.png" mode=""></image>
			<text>暂无数据</text>
		</view>
	</view>
</template>

<script>
	export default {
		name: '',
		data() {
			return {
				key: '',
				goodList: [{},
					{},
					{},
					{},
					{},
					{},
				]
			}
		},
		onLoad(val) {
			console.log(val)
			this.key = val.search
			console.log((this.key))
		}
	}
</script>

<style lang="scss" scoped>
	.goodBox {
		display: flex;
		flex-wrap: wrap;

		.searchList {
			width: 50%;
			margin-top: 18rpx;

			.goodContent {
				width: 95%;
				margin: 0 auto;
				background: #FFFFFF;
				border-radius: 10px;
				min-height: 400rpx;
				padding-bottom: 20rpx;

				.bgImg {
					image {
						width: 100%;
						height: 336rpx;
						background: #C6CA53;
						border-radius: 10rpx 10rpx 0rpx 0rpx;
					}
				}

				.goodsInfo {
					width: 100%;
					display: flex;
					flex-wrap: wrap;
					word-wrap: break-word;
					word-break: normal;
					font-size: 29rpx;
					font-family: Source Han Sans CN;
					font-weight: 400;
					color: #222222;
					-webkit-line-clamp: 2;
					display: -webkit-box;
					-webkit-box-orient: vertical;
					overflow: hidden;
					text-overflow: ellipsis;
					margin: 20rpx 0;

					.label {
						width: fit-content;
						padding: 0 10rpx;
						background: linear-gradient(90deg, #FFA41E, #FF5049);
						font-size: 22rpx;
						color: #FFF;
						border-radius: 5rpx;
					}
				}

				.Tips {
					height: 33rpx;
					background: #FFEAE6;
					border-radius: 6rpx;
					font-size: 22rpx;
					font-family: Source Han Sans CN;
					font-weight: 500;
					color: #FF000C;
					width: fit-content;
					padding: 0 10rpx;
					line-height: 33rpx;
				}
			}
		}
	}

	.noData {
		width: 750rpx;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		image {
			width: 400rpx;
			height: 400rpx;
		}
	}
</style>