<template>
	<view class="page">
		<view class="app-content">
			<view class="app-items">
				<view class="banana">
					<h2 style="color: #2384E8">找电影</h2>
					<span>影院热映</span>
				</view>
				<view class="banana">
					<h2 style="color: #7A6ADB">热播剧</h2>
					<span>剧集综艺</span>
				</view>
				<view class="banana">
					<h2 style="color: #9F7860">畅销书</h2>
					<span>畅销排行</span>
				</view>
				<view class="banana">
					<h2 style="color: #2AB8CC">找小组</h2>
					<span>志趣相投</span>
				</view>
				<view class="banana">
					<h2 style="color: #F48F2E">找音乐</h2>
					<span>新碟榜</span>
				</view>
				<view class="banana">
					<h2 style="color: #42BD56">豆品</h2>
					<span>生活美学</span>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '主页'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="less" scoped>
	.app-content {
		padding: 30rpx 36rpx 0;
		.app-items {
			border-radius: 8rpx;
			border: 2rpx solid rgba(236, 236, 236, 1);
			display: flex;
			justify-content: space-between;
			flex-wrap: wrap;
			.banana {
				width: 33.3%;
				box-sizing: border-box;
				text-align: center;
				padding: 36rpx 0 32rpx;
				border-right: 2rpx solid rgba(236, 236, 236, 1);
				border-bottom: 2rpx solid rgba(236, 236, 236, 1);
				&:nth-child(3n) {
					border-right: 0;
				}
				&:nth-child(n+4) {
					border-bottom: 0;
				}
				h2 {
					font-weight: 500;
					font-size: 38rpx;
					line-height: 52rpx;
					margin-bottom: 4rpx;
				}
				span {
					display: block;
					color: #818181;
					font-size: 26rpx;
					line-height: 34rpx;
					letter-spacing: 2rpx;
				}
			}
		}
	}
</style>
