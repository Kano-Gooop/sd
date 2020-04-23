<template>
	<view>
		<view class="top">
			<view class="search-box">
				<image src="../../static/icons/zoom.png"></image>
				搜索
			</view>
			<view class="bell">
				<image src="/static/icons/bell.png"></image>
				<view class="red-dot"></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hellos222哄哄'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.top {
		padding: 16rpx 29rpx 16rpx 24rpx;
		background: #ffbe00;
		display: flex;
		align-items: center;
		
		.search-box {
			background: #fff;
			-webkit-border-radius: 10rpx;
			-moz-border-radius: 10rpx;
			border-radius: 10rpx;
			flex-grow: 1;
			display: flex;
			align-items: center;
			justify-content: center;
			font-size: 26rpx;
			color: #b2b2b2;
			height: 56rpx;
			
			image {
				width: 25rpx;
				height: 25rpx;
				margin-right: 15rpx;
			}
		}
		
		.bell {
			margin-left: 24rpx;
			position: relative;
			
			image {
				width: 40rpx;
				height: 50rpx;
				vertical-align: bottom;
			}
			
			.red-dot {
				width: 14rpx;
				height: 14rpx;
				border: 3rpx solid #ffbe00;
				-webkit-border-radius: 50%;
				-moz-border-radius: 50%;
				border-radius: 50%;
				background: #ff4032;
				position: absolute;
				top: 4rpx;
				right: 0;
			}
		}
	}
</style>