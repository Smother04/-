<template>
	<view class="bgf7 border-box vh100">
		<view class="flex flex-between align-center bgfff pdlr30"
			style="height: 124rpx;border-radius: 0 0 40rpx 40rpx;">
			<view class="flex align-center">
				<image class="" src="../../static/home/3701.png" style="width: 25rpx;height: 28rpx;" mode=""></image>
				<text class="ml8 font28 fontw700">定位地址</text>
			</view>
			<view class="flex flex-between align-center bdrd36"
				style="width: 514rpx;height: 70rpx;border: 2px solid #FFD719;">
				<image class=" mrr26" src="../../static/home/search.png"
					style="width: 25rpx;height: 25rpx;margin-left:25rpx" mode=""></image>
				<view class="" style="border-right:1rpx solid #ccc; height: 40rpx;"> </view>
				<input class="flex1 mrl24 font28" type="text" @focus="searchChange" placeholder="搜索商品"
					v-model="keyword">
				<view class="searchBtn bdrd36" style="width: 112rpx;height: 70rpx;">
					<u-button shape="circle" color="#FEDC3F" text="搜索" @click="searchChange"></u-button>
				</view>
			</view>
		</view>
		<view class="botbox mrt20">
			<view class="leftbox">
				<scroll-view scroll-y="true" style="height:calc(100vh - 400rpx);" @scrolltoupper="upper">
					<view class="flex pd24" v-for="(item,index) in classiftList" :key="item.id"
						@click="activeclassify(index)" :class="currone==index ? 'actived' : '' ">
						{{item.name}}
					</view>
				</scroll-view>
			</view>
			<view class="rightbox">
				<scroll-view class="swipertwo" scroll-y="true" v-if="categorize2.length>0"
					style="height:calc(100vh - 145rpx);">
					<view class="rightswiper" v-for="(item,index) in categorize2"
						:key="item.id">
						<view class="">
							<image style="width: 214rpx;height: 214rpx;" src="../../static/classify/组 3980.png" mode="">
							</image>
						</view>

						<view class="classifyInfo">
							<text class="font26 fontw500 col222">{{item.title}}</text>
							<text class="font22 col888">机构：{{item.message}}</text>
							<view class="agebox">
								<text class="font24 fontw500 col222">适龄：{{item.age}}岁</text>
								<view class="readbox">查看</view>
							</view>
						</view>
					</view>
				</scroll-view>
				<!-- 空 -->
				<kong v-else></kong>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				keyword: "",
				wh: '',
				currone: 0,
				classiftList: [{
						name: '早教类',
					}, {
						name: '游泳类',
					}, {
						name: '其他类',
					}, {
						name: '早教类',
					},

				],
				categorize2: [{
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, {
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, {
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, {
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, {
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, {
					title: '儿童中国舞蹈课程3节',
					message: '童学馆儿童成长中心',
					age: '0-3'
				}, ]
			}
		},
		onLoad() {

		},
		methods: {
			// 去搜索
			searchChange() {
				uni.navigateTo({
					url: '/pages/search/search'
				})
			},
			activeclassify(index) {
				this.currone = index
				this.categorize2 = this.categorize2.map((item, index2) => {
					return {
						text: index
					}
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	/deep/ .searchBtn .u-button {
		width: 100%;
		height: 100%;
	}

	.botbox {
		width: 750rpx;
		display: flex;

		.leftbox {
			width: 176rpx;

			.actived {
				background: #fff;
				background-image: url('../../static/classify/椭圆 449.png');
				background-repeat: no-repeat;
				border-radius: 40rpx 0 0 40rpx;
			}
		}

		.rightbox {
			width: calc(100% - 176rpx);

			.swipertwo {
				.rightswiper {
					display: flex;
					align-items: center;
					padding: 26rpx 30rpx 0 28rpx;
					background: #fff;
					.classifyInfo{
						display: flex;
						flex-direction: column;
						justify-content: space-around;
						width: 278rpx;
						height: 214rpx;
						margin-left: 24rpx;
						
						.agebox{
							display: flex;
							justify-content: space-between;
							height: 44rpx;
							.readbox{
								width: 96rpx;
								height: 44rpx;
								background: #FC7032;
								text-align: center;
								line-height: 44rpx;
								border-radius: 44rpx;
								font-size: 26rpx;
								color: #fff;
							}
						}
					}
				}
			}
		}
	}
</style>