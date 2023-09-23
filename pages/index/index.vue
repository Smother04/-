<template>
	<view class="" style="background: #F7F7F7;">
		<view class="" style="height: 750rpx;">
			<image class="absolute w100" src="../../static/home/homebg.png" style="z-index:1; height:574rpx;"> </image>
			<view class="absolute  w100" style="z-index:2; height:750rpx;">
				
				<!-- 自定义导航 -->
				<view class="flex px30 flex-between align-center"
					:style="{'height': autoHeight + 'px', 'padding-top': sysHeight + 'px'}">
					<view class="flex align-center">
						<image class="" src="../../static/home/3701.png" style="width: 25rpx;height: 28rpx;" mode="">
						</image>
						<text class="ml8 font28 fontw700">定位地址</text>
					</view>
					<view class="font36 fontw700 colorfff mr150">
						首页
					</view>
					<view class=""></view>
				</view>
				<!-- 自定义导航栏 -->

				<!-- 搜索框 -->
				<view class="flex flex-between align-center mr30 bgfff"
					style="width: 690rpx;height: 70rpx;border-radius: 35rpx;">
					<image class=" mrr26" src="../../static/home/search.png"
						style="width: 25rpx;height: 25rpx;margin-left:25rpx" mode=""></image>
					<view class="" style="border-right:1rpx solid #ccc; height: 40rpx;"> </view>
					<input class="flex1 mrl24 font28" @focus="searchChange" type="text" placeholder="搜索商品"
						v-model="keyword">
					<view class="searchBtn" style="width: 112rpx;height: 62rpx;margin-right: 4rpx;"
						@click="searchChange">
						<u-button shape="circle" color="#FEDC3F" text="搜索"></u-button>
					</view>
				</view>
				<!-- 搜索框 -->
				
				<!-- 滑块 -->
				<view class="">
					<scroll-view class="flex ml30 mrt22 font28 fontw400 col555"
						style="white-space: nowrap; width: 100%;" scroll-x="true">
						<view class="inline bdrd30 mrr30 text-align"
							style="width: 164rpx;height: 52rpx;line-height: 52rpx;background: #fff;opacity: 0.6;">
							水上乐园
						</view>
						<view class="inline bdrd30 mrr30 text-align"
							style="width: 164rpx;height: 52rpx;line-height: 52rpx;background: #fff;opacity: 0.6;">
							室内乐园
						</view>
						<view class="inline bdrd30 mrr30 text-align"
							style="width: 164rpx;height: 52rpx;line-height: 52rpx;background: #fff;opacity: 0.6;">
							亲子旅游
						</view>
						<view class="inline bdrd30 mrr30 text-align"
							style="width: 164rpx;height: 52rpx;line-height: 52rpx;background: #fff;opacity: 0.6;">
							生活服务
						</view>
						<view class="inline bdrd30 mrr30 text-align"
							style="width: 164rpx;height: 52rpx;line-height: 52rpx;background: #fff;opacity: 0.6;">
							水上乐园
						</view>
					</scroll-view>
				</view>
				<!-- 滑块 -->

				<!-- 轮播图 -->
				<view class="mr30 mrt16">
					<u-swiper class="" :height="314" :list="swiperlist" :indicator="true" indicatorMode="dot"
						indicator-pos="bottomRight"></u-swiper>
				</view>
				<!-- 轮播图 -->

				<!-- 菜单 -->
				<view class="flex flex-between mr30" style="width: 690rpx;margin-top: 28rpx;background: #F7F7F7;">
					<view class="flex flex-colum flex-between align-center bgfff">
						<image src="../../static/home/组 6406.png" style="width: 96rpx;height: 96rpx;" mode=""></image>
						<text class="font28 fontw400">景区户外</text>
					</view>
					<view class="flex flex-colum flex-between align-center bgfff">
						<image src="../../static/home/组 6407.png" style="width: 96rpx;height: 96rpx;" mode=""></image>
						<text class="font28 fontw400">商场遛娃</text>
					</view>
					<view class="flex flex-colum flex-between align-center bgfff">
						<image src="../../static/home/组 6408.png" style="width: 96rpx;height: 96rpx;" mode=""></image>
						<text class="font28 fontw400">亲子酒店</text>
					</view>
					<view class="flex flex-colum flex-between align-center bgfff">
						<image src="../../static/home/组 6409.png" style="width: 96rpx;height: 96rpx;" mode=""></image>
						<text class="font28 fontw400">演出剧展</text>
					</view>
					<view class="flex flex-colum flex-between align-center bgfff">
						<image src="../../static/home/组 6410.png" style="width: 96rpx;height: 96rpx;" mode=""></image>
						<text class="font28 fontw400">儿童服务</text>
					</view>
				</view>
				<!-- 菜单 -->

			</view>
		</view>
		<view class="relative mr30" style="width: 690rpx;height: 500rpx;margin-top: 38rpx;">
			<image class="absolute w100" src="../../static/home/组 6411.png" style="z-index: 1;height: 500rpx;" mode="">
			</image>
			<view class="absolute flex flex-colum flex-between align-center w100" style="z-index: 2;height: 500rpx;">
				<text class="font56 fontw400"
					style="margin-top: 38rpx;color: #F94D29;font-family: LogoSC LongZhuTi-Regular, LogoSC LongZhuTi;">热门爆品狂欢</text>
				<image src="../../static/home/组 6412.png" @click="meetRoom" style="width: 258rpx;height: 88rpx;" mode=""></image>
				<view class="flex flex-between w100">
					<view class="flex flex-colum bdrd12 bd2" style="background: #fff;height: 270rpx;width: 162rpx;">
						<image src="../../static/home/组 6406@2x.png" style="width: 162rpx;height: 162rpx;" mode="">
						</image>
						<view class="ml10">
							<text class="font28 fontw400 fontfa1">华侨城玛雅</text>
							<text class="font36 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
						</view>
					</view>
					<view class="flex flex-colum bdrd12 bd2" style="background: #fff;height: 270rpx;width: 162rpx;">
						<image src="../../static/home/组 6406@2x.png" style="width: 162rpx;height: 162rpx;" mode="">
						</image>
						<view class="ml10">
							<text class="font28 fontw400 fontfa1">华侨城玛雅</text>
							<text class="font36 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
						</view>
					</view>
					<view class="flex flex-colum bdrd12 bd2" style="background: #fff;height: 270rpx;width: 162rpx;">
						<image src="../../static/home/组 6406@2x.png" style="width: 162rpx;height: 162rpx;" mode="">
						</image>
						<view class="ml10">
							<text class="font28 fontw400 fontfa1">华侨城玛雅</text>
							<text class="font36 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
						</view>
					</view>
					<view class="flex flex-colum bdrd12 bd2" style="background: #fff;height: 270rpx;width: 162rpx;">
						<image src="../../static/home/组 6406@2x.png" style="width: 162rpx;height: 162rpx;" mode="">
						</image>
						<view class="ml10">
							<text class="font28 fontw400 fontfa1">华侨城玛雅</text>
							<text class="font36 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="relative  mr30 mrt30 bdrd30 overhiden"
			style="z-index: 1; width: 690rpx;height: 428rpx;background: #FFFCEF;">

			<view class="absolute flex flex-colum flex-between w100 h100" style="z-index: -1;">
				<view class="flex flex-between">
					<image class="" src="../../static/home/蒙版组 502.png" style="width: 150rpx;height: 116rpx;" mode="">
					</image>

					<image class="" src="../../static/home/蒙版组 501.png" style="width: 246rpx;height: 116rpx;" mode="">
					</image>
				</view>
				<view class="">
					<image src="../../static/home/蒙版组 503.png" style="width: 238rpx;height: 150rpx;margin-left: 170rpx;"
						mode=""></image>
				</view>
			</view>

			<view class="border-box  w100 flex flex-between pd20 pdt30 pdb24" style="height: 86rpx;">
				<view class="relative">
					<text class="font32 fontw500">南昌周边亲子游</text>
					<image class="absolute" src="../../static/home/组 6413@2x.png"
						style="width: 70rpx;height: 50rpx;bottom: -20%;right: -20%; z-index:-1" mode=""></image>
				</view>
				<view class="flex align-center" @click="gotravel()">
					<text class="font24">更多</text>
					<image src="../../static/home/组 6415.png" mode=""
						style="width: 16rpx;height: 9rpx;padding-left: 10rpx;">
					</image>
				</view>
			</view>
			<view class="flex flex-around">
				<view class="flex flex-colum bdrd12" style="background: #fff;width: 214rpx;height: 318rpx;">
					<image class="w100" src="../../static/home/sp20230913_172329_178.png" mode=""></image>

					<view class="mr10">
						<text class="font28 fontw400 fontfa1">庐山纯玩2日游</text>
						<view class="flex flex-between align-center">
							<text class="font24 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
							<text class="font20 col888">已售1000</text>
						</view>
					</view>
				</view>
				<view class="flex flex-colum bdrd12" style="background: #fff;width: 214rpx;height: 318rpx;">
					<image class="w100" src="../../static/home/sp20230913_172329_178.png" mode=""></image>

					<view class="mr10">
						<text class="font28 fontw400 fontfa1">庐山纯玩2日游</text>
						<view class="flex flex-between align-center">
							<text class="font24 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
							<text class="font20 col888">已售1000</text>
						</view>
					</view>
				</view>
				<view class="flex flex-colum bdrd12" style="background: #fff;width: 214rpx;height: 318rpx;">
					<image class="w100" src="../../static/home/sp20230913_172329_178.png" mode=""></image>

					<view class="mr10">
						<text class="font28 fontw400 fontfa1">庐山纯玩2日游</text>
						<view class="flex flex-between align-center">
							<text class="font24 fontw500 fontfa2" style="color: #F94D29;">￥29</text>
							<text class="font20 col888">已售1000</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="mr30 mrt20 bdrd30" style="width: 690rpx;height: 514rpx;background: #fff;">
			<view class="border-box w100 flex flex-between pd20 pdt34">
				<view class="relative">
					<image class="absolute" src="../../static/home/组 6414.png" style="width: 212rpx;height: 40rpx;"
						mode="">
					</image>
				</view>
				<view class="flex align-center" @click="tripUnlike()">
					<text class="font24">更多</text>
					<image src="../../static/home/组 6415.png" mode=""
						style="width: 16rpx;height: 9rpx;padding-left: 10rpx;">
					</image>
				</view>
			</view>
			<view class="flex flex-between mr14 mrt20 mrb20 bdrd32 overhiden"
				style="width: 662rpx;height: 404rpx;background: #FFBBBB;">
				<view class="bdrd32 overhiden">
					<swiper class="uni-swiper-wrapper" style="width: 404rpx;height: 404rpx;" circular
						:indicator-dots="true" :autoplay="true" :interval="interval" indicator-color="#fff"
						indicator-active-color="#FEDC3F">
						<swiper-item>
							<view class="h100 w100">
								<image style="width: 100%;height: 100%;"
									src="../../static/home/sp20230914_085703_635.png" mode=""></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="h100 w100">
								<image style="width: 100%;height: 100%;"
									src="../../static/home/sp20230914_085703_635.png" mode=""></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="h100 w100">
								<image style="width: 100%;height: 100%;"
									src="../../static/home/sp20230914_085703_635.png" mode=""></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="h100 w100">
								<image style="width: 100%;height: 100%;"
									src="../../static/home/sp20230914_085703_635.png" mode=""></image>
							</view>
						</swiper-item>
					</swiper>
				</view>
				<view class="bdrd22 mr26 mrt26" style="width: 206rpx;height: 300rpx;background: #4D2F25;">
					<view class="mrl12 mrr14 flex flex-colum flex-around" style="width: 180rpx; height: 268rpx;">
						<view class="font30 colfff fontw400">南昌海洋公园一大一小一日游</view>
						<view class="font24 colfff" style="text-decoration: line-through;">￥288</view>
						<view class="font36 fontw500" style="color: #FF3D46;">￥189</view>
					</view>
					<button class="bdrd18 font28"
						style="width: 168rpx;height: 62rpx;line-height: 62rpx;color:#ffffff;background:#FF3D46;">立马抢购</button>
				</view>
			</view>
		</view>
		<view class="">
			<scroll-view scroll-x="true" class="w100" style="white-space: nowrap;">
				<view class="flex pd24" @click="activeClick(index)" :class="[active == index ? 'active' : '']"
					v-for="(item,index) in list4" :key="index" style="display: inline-block;">
					<view class="flex flex-between align-center">
						<view class="mrr24">
							<text class="font32 fontw500 col222">{{item.name}}</text>
							<view class="font24 mrt16 fontw400 col555 text-align">
								<text>{{item.title}}</text>
							</view>
						</view>
						<view class="" style="border-right: 2px solid #E2E2E2;height: 56rpx;"></view>
					</view>
				</view>
			</scroll-view>

			<!-- 热门推荐 -->
			<view class="mr30 flex flex-between flex-wrap" style="width: 690rpx;background: #F7F7F7;">
				<view class="flex flex-colum flex-between bdrd20 mrb20 bgfff" v-for="(item,index) in contentList"
					:key="index" style="width: 336rpx;height: 512rpx;">

					<image class="overhiden" src="../../static/home/sp20230914_150137_567.png"
						style="width: 336rpx;height: 336rpx;" mode=""></image>

					<view class="mr14 font30 mrt24" style="width: 312rpx;">
						<text>{{item.title}}</text>
					</view>
					<view class="mr14 mrb20">
						<text class="font40 mrr14" style="color: #F94D29;">{{item.price}}</text>
						<text class="font20 col888" style="text-decoration: line-through;">{{item.originalPrice}}</text>
					</view>
				</view>
			</view>
			<!-- 热门推荐 -->
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				autoHeight: 0,
				sysHeight: 0,
				keyword: '',
				interval: 2000,
				duration: 500,
				swiperlist: [
					'https://cdn.uviewui.com/uview/swiper/swiper3.png',
					'https://cdn.uviewui.com/uview/swiper/swiper2.png',
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
				],
				active: 0,
				list4: [{
						name: '热门推荐',
						title: '限时抢购'
					}, {
						name: '游乐场',
						title: '欢乐天堂'
					}, {
						name: '热门景点',
						title: '周边游'
					}, {
						name: '数字教育',
						title: '教育服务'
					}, {
						name: '周边福利',
						title: '限时抢购'
					}, 
				],
				contentList: [{
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					}, {
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					}, {
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					}, {
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					}, {
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					}, {
						title: '万科时代广场/万象城商业',
						price: '29.00',
						originalPrice: '36.00'
					},

				]
			}
		},
		onLoad() {
			this.init()
		},
		methods: {
			activeClick(index) {
				this.active = index
			},
			searchChange() {
				uni.navigateTo({
					url: '/pages/search/search'
				})
			},
			initNavBarInfo() {
				// 获取设备的系统信息高度
				let sys = uni.getSystemInfoSync()
				this.sysHeight = sys.statusBarHeight
				// 获取移动端菜单按钮的高度
				let rect = uni.getMenuButtonBoundingClientRect()
				if (rect === undefined) {
					this.autoHeight = 60
					// this.searchWidth = sys.screenWidth - 100
				} else {
					// 计算自定义的导航栏高度
					this.autoHeight = (rect.top - sys.statusBarHeight) * 2 + rect.height
					// this.searchWidth = sys.screenWidth - 100 - rect.width * 1.3
				}
			},
			// 去会场
			meetRoom(){
				uni.navigateTo({
					url: "/pages/meetroom/meetroom"
				})
			},
			// 更多亲子游
			gotravel(){
				uni.navigateTo({
					url: '/pages/familytrip/familytrip'
				})
			},
			// 更多不一样
			tripUnlike(){
				uni.navigateTo({
					url: '/pages/tripUnlike/tripUnlike'
				})
			},
			init() {
				this.initNavBarInfo()
			}
		}
	}
</script>

<style scoped lang="scss">
	::v-deep .searchBtn .u-button {
		width: 100%;
		height: 100%;
	}

	.uni-swiper-wrapper {
		::v-deep .uni-swiper-dots {
			// 指示点整个区域的位置
			left: 320rpx;
		}

		::v-deep .uni-swiper-dot {
			// 指示点元素默认样式
			width: 24rpx !important; //  比较原先代码 - 修改后为18upx
			height: 8rpx !important; //  比较原先代码 - 修改后为18upx
			border-radius: 4rpx;
			// border: 1rpx solid #E0B079;
		}

		::v-deep .uni-swiper-dot-active {
			// 指示点元素激活（当前选中）状态样式
			// background: #CD9763;
			width: 12rpx !important; // 比较原先代码 - 修改后为40upx
			height: 12rpx !important;
			border-radius: 50%;
		}
	}

	.active {
		background: url('../../static/home/路径 4984.png') no-repeat center;
	}
</style>