<template>
	<view class="bgf7 page flex flex-colum flex-between">
		<view class="">
			<view class="pdx30 bgfff" style="height: 748rpx;border-radius: 0 0 12rpx 12rpx;">
				<view class="flex flex-colum flex-between pdy30" style="height: 688rpx;">
					<view class="upload flex flex-colum align-center flex-center"
						style="width: 260rpx;height: 260rpx;border: 2rpx dashed #999999;" @click="uploadMedia()">
						<view class="">
							<image style="width: 66rpx;height: 60rpx;" src="../../static/publish/4800.png" mode="">
							</image>
						</view>
						<view class="mrt28 font28 fontw400 col888">
							<text>添加图片/视频</text>
						</view>
					</view>
					<view class="font32 fontw400 col888">
						<input type="text" placeholder="填写标题会有更多赞哦~"></input>
					</view>
					<view class="" style="border-bottom: 2rpx solid #F1F1F1;">
						
					</view>
					<view class="font28 fontw400 col888">
						<textarea placeholder="添加正文" style="width: 100%;" cols="30" rows="10"></textarea>
					</view>
				</view>
			</view>
			<view class="font28 col555 bgfff mrt18">
				<view class="w100 flex flex-between align-center border-box px30" style="height: 100rpx;"
					@click="show=true">
					<view class="">
						<u-action-sheet :show="show" @select="selectClick" @close="show=false" :actions="list"
							cancelText="取消"></u-action-sheet>
						<text>{{title}}</text>
					</view>
					<u-icon name="/static/publish/5198.png" :width="16" :height="32"></u-icon>
				</view>
			</view>
		</view>
		<view class="flex flex-center align-center mx30 mrb56"
			style="width: 690rpx;height: 86rpx;background: #FFD719;border-radius: 83rpx;">
			<text class="font36 fontw500 col222">发布种草</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '选择分类',
				list: [{
						name: '风景'
					},
					{
						name: '旅游'
					},
					{
						name: '家乡特色'
					},
					{
						name: '异域风情'
					},
				],
				show: false
			};
		},
		methods: {
			selectClick(index) {
				console.log(index)
				this.title = index.name
			},
			uploadMedia() {
				uni.chooseMedia({
					count: 9,
					mediaType: ['image', 'video'],
					sourceType: ['album', 'camera'],
					maxDuration: 30,
					camera: 'back',
					success(res) {
						console.log(res.tempFiles)
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	.upload {
		background: transparent;
	}
</style>