<template>
	<view class="vh100 bgf7">

		<!-- 搜索框 -->
		<view class="searchBox">
			<view class="search flex flex-between">
				<view class="leftbox">
					<image class="scan" src="../../static/home/search.png" mode=""></image>
					<view style="border-right:1rpx solid #E6E6E6; height: 40rpx;"> </view>
				</view>
				<view class="font28 input">
					<input class="searchContent" type="text" placeholder="搜索商品" v-model="value">
					<button class="searchBtn font28" @click="goSearch">搜索</button>
				</view>
			</view>
		</view>
		<!-- 搜索框 -->

		<!-- 历史搜索，推荐搜索 -->
		<view class="searchHis flex flex-colum flex-between">
			<view class="historybox flex flex-colum flex-between">
				<view class="flex flex-between">
					<text class="font32 fontw500 col222">历史搜索</text>
					<image style="width: 28rpx;height: 30rpx;" @click="clearHistory"
						src="../../static/search/组 4640@2x.png" mode=""></image>
				</view>
				<view class="history">
					<view v-for="(item,i) in searchList.slice(0,4)" :key="i" class="item" @click="searchTag(i)">
						{{item}}
					</view>
				</view>
			</view>
			<view class="recombox flex flex-colum flex-between">
				<view class="flex flex-between">
					<text class="font32 fontw500 col222">推荐搜索</text>
					<view class=""></view>
				</view>
				<view class="flex flex-wrap" style="width: 100%;height: 158rpx;">
					<view class="recomcontent font28" v-for="(item,index) in list.slice(0,6)" :key="index">
						{{item.title}}
					</view>
				</view>
			</view>
		</view>
		<!-- 历史搜索，推荐搜索 -->

		<!-- 热门搜索 -->
		<view class="">
			<scroll-view class="hotSearch" scroll-x="true">
				<view class="hotList" v-for="(item,index) in hotList" :key="index">
					<view class="bgImg absolute" style="height: 146rpx;width: 520rpx;">
						<image style="width: 25rpx;height: 32rpx;margin-right: 14rpx;"
							src="../../static/search/路径 4058.png" mode="">
						</image>
						{{item.title}}
					</view>
					<scroll-view class="scrollybox" style="width: 520rpx;margin-top: 70rpx;" scroll-y="true">
						<view class="hotbox" v-for="(obj,i) in objlist" :key="i">
							<view class="flex align-center">
								<view class="rank font20" style="width: 28rpx;height: 28rpx;">
									{{obj.sum}}
								</view>
								<text class="font28" style="margin: 0 14rpx;">{{obj.hotName}}</text>
								<view class="hot font20" style="width: 38rpx;height: 30rpx;">
									热
								</view>
							</view>
							<image style="width: 12rpx;height: 20rpx;" :src="obj.icon" mode="">
							</image>
						</view>
					</scroll-view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value: '',
				searchList: [],
				list: [{
						title: '早餐奶'
					},
					{
						title: '女装衣服'
					},
					{
						title: '青年旅游'
					},
					{
						title: '奶茶'
					}, {
						title: '奶茶'
					}, {
						title: '奶茶'
					},
				],
				hotList: [{
						title: '热门搜索'
					},
					{
						title: '吃货清单'
					},
					{
						title: '吃货清单'
					},
					{
						title: '吃货清单'
					},
				],
				objlist: [{
					sum: 1,
					hotName: '防疫物品清单',
					icon: '../../static/search/路径 4328.png'
				}, {
					sum: 2,
					hotName: '轻薄风衣羽绒服',
					icon: '../../static/search/路径 4329.png'
				}, {
					sum: 3,
					hotName: '鱼骨卫衣',
					icon: '../../static/search/路径 4328.png'
				}, {
					sum: 4,
					hotName: '雅痞男士的日常',
					icon: '../../static/search/路径 4328.png'
				}, {
					sum: 5,
					hotName: '世界杯纹身贴',
					icon: '../../static/search/路径 4329.png'
				}, ]
			}
		},
		methods: {
			// 初始化搜索历史，将本地缓存的历史记录同步到页面
			init() {
				this.searchList = uni.getStorageSync('searchList') || []
			},
			// 去搜索商品列表页面
			goSearch() {
				if (this.value !== '') {
					uni.navigateTo({
						url: '/pages/search/searchGoodList?search=' + this.value
					})
					console.log(this.value)
					// 判断历史记录是否重复
					if (this.searchList.indexOf(this.value) == -1) {
						this.searchList.unshift(this.value)
						// 同步搜索历史到本地缓存
						uni.setStorageSync('searchList', this.searchList)
					}
				}
			},
			searchTag(i){
				// uni.setStorageSync('value', this.searchList[i])
				// console.log(uni.getStorageSync("searchList"))
				let hisList = uni.getStorageSync("searchList")
				this.value = hisList[i]
				
				uni.navigateTo({
					url: '/pages/search/searchGoodList?search=' + this.value ,
					success: () => {
						// 点击的tag移到数组最前方
						this.searchList.map((item, j) => {
							if (j == i) {
								this.searchList.unshift(this.searchList.splice(i, 1)[0]);
							}
						})
						uni.setStorageSync('searchList', this.searchList)
					}
				})
			},
			// 删除历史记录
			clearHistory() {
				uni.showModal({
					title: '提示',
					content: '确认删除历史记录吗？',
					success: res => {
						if (res.confirm) {
							uni.removeStorage({
								key: 'searchList'
							})
							this.searchList = []
						} else if (res.cancel) {

						}
					}
				})
			}
		},
		created() {
			this.init()
		}
	}
</script>

<style lang="scss" scoped>
	.searchBox {
		width: 690rpx;
		height: 128rpx;
		padding-left: 30rpx;
		padding-right: 30rpx;
		border-radius: 0 0 20rpx 20rpx;
		background: #FFF;

		.search {
			width: 100%;
			height: 70rpx;
			margin-top: 28rpx;
			border-radius: 36rpx;
			border: 2px solid #FFD719;

			.leftbox {
				display: flex;
				justify-content: center;
				align-items: center;
				padding-right: 24rpx;

				.scan {
					width: 25rpx;
					height: 25rpx;
					margin-left: 25rpx;
					margin-right: 25rpx;
				}
			}

			.input {
				display: flex;
				justify-content: space-between;
				align-items: center;
				width: calc(100% - 100rpx);
				height: 70rpx;

				.searchContent {
					width: 478rpx;
				}

				.searchBtn {
					width: 112rpx;
					height: 70rpx;
					border-radius: 36rpx;
					background: #FEDC3F;
				}
			}
		}
	}

	.searchHis {
		width: 690rpx;
		height: 378rpx;
		margin: 42rpx 0 36rpx 0;
		padding-left: 28rpx;
		padding-right: 30rpx;

		.historybox {
			width: 100%;
			height: 120rpx;

			.history {
				display: flex;
				justify-content: left;
				align-items: center;
				flex-wrap: wrap;

				.item {
					width: 128rpx;
					height: 64rpx;
					line-height: 64rpx;
					text-align: center;
					background: #FFF;
					border-radius: 64rpx;
					margin-right: 30rpx;
				}
			}
		}

		.recombox {
			width: 100%;
			height: 220rpx;

			.recomcontent {
				width: 180rpx;
				height: 64rpx;
				line-height: 64rpx;
				text-align: center;
				background: #FFF;
				border-radius: 64rpx;
				margin-right: 30rpx;
			}
		}
	}

	.hotSearch {
		width: 100%;
		height: 952rpx;
		display: flex;
		white-space: nowrap;
		background: #F7F7F7;

		.hotList {
			width: 520rpx;
			height: 952rpx;
			margin-left: 30rpx;
			display: inline-block;
			background: #FFF;
			border-radius: 20rpx;

			.bgImg {
				box-sizing: border-box;
				padding-left: 20rpx;
				padding-top: 28rpx;
				padding-right: 20rpx;
				background: url('../../static/search/蒙版组 248.png') no-repeat;
				background-size: cover;
				background-position: center;
			}
		}
	}

	.hotbox {
		height: 94rpx;
		margin: 0 20rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		border-bottom: 1px dashed #ECECEC;

		.rank {
			color: #FFF;
			background: #FC3406;
			border-radius: 6rpx;
			border: 1px solid #FF6D4E;
			text-align: center;
			line-height: 28rpx;
		}

		.hot {
			color: #F94D29;
			background: #FFE6E1;
			border-radius: 6rpx;
			border: 1px solid #FF6D4E;
			text-align: center;
			line-height: 28rpx;
		}
	}
</style>