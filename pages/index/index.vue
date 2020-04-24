<template>
	<view>
		<!-- 头部搜索框 -->
		<view class="top">
			<view class="search-box">
				<image src="../../static/icons/zoom.png"></image>
				<text>搜索</text>
			</view>
			<view class="bell">
				<image src="../../static/icons/bell.png"></image>
				<view class="red-dot"></view>
			</view>
		</view>

		<!-- 轮播图 -->
		<swiper class="swiper" :indicator-dots="true" :autoplay="true">
			<swiper-item>
				<image src="../../static/t-images/swiper1.jpg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/t-images/swiper2.jpg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/t-images/swiper3.jpg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/t-images/swiper4.jpg" mode="aspectFill"></image>
			</swiper-item>
		</swiper>

		<!-- 金刚区 -->
		<view class="kingkong">
			<navigator url="/chou-package/pages/chou-list/chou-list">
				<image src="../../static/icons/kk-chou.png"></image>
				<view class="title">创意众筹</view>
			</navigator>
			<navigator url="/pages/member-tehui/member-tehui">
				<image src="../../static/icons/kk-member.png"></image>
				<view class="title">会员特惠</view>
			</navigator>
			<navigator url="/ip-package/pages/index/index">
				<image src="../../static/icons/kk-ip.png"></image>
				<view class="title">IP授权</view>
			</navigator>
			<navigator url="/purchase-package/pages/index/index">
				<image src="../../static/icons/kk-purchase.png"></image>
				<view class="title">即时采购</view>
			</navigator>
			<navigator url="/activity-package/pages/activity-list/activity-list">
				<image src="../../static/icons/kk-match.png"></image>
				<view class="title">文创大赛</view>
			</navigator>
		</view>

		<view class="hr"></view>

		<!-- 视频精选 -->
		<view class="video-box">
			<view class="title-line">
				<view class="title">视频精选</view>
				<view class="more">
					更多
					<image src="../../static/icons/right.png"></image>
				</view>
			</view>
			<view class="video-list">
				<view class="video" v-for="i in 3">
					<view class="cover-box">
						<image src="../../static/t-images/swiper1.jpg" class="cover" mode="aspectFill"></image>
						<view class="mask">
							<view class="play"></view>
						</view>
					</view>
					<view class="info">
						<view class="title one-line">中国国家博物馆溪山雨意快客杯功夫茶具套装中国国家博物馆溪山雨意快客杯功夫茶具套装</view>
						<view class="price-and">
							<view class="price">￥299.00</view>
							<image src="../../static/icons/heart.png" class="heart"></image>
						</view>
					</view>
				</view>
			</view>
		</view>

		<div class="hr"></div>

		<!-- 定制专区 -->
		<view class="custom-box">
			<view class="title">定制专区</view>
			<view class="tabs">
				<view class="tab active">免费打样专区</view>
				<view class="tab">小批量定制</view>
				<view class="tab">免开模费</view>
			</view>
			<view class="product-list">
				<view class="product" v-for="i in 5">
					<image src="../../static/t-images/swiper1.jpg" class="cover" mode="aspectFill"></image>
					<view class="info">
						<view class="title one-line">来图来样定做帆布包 免费来图来样定做帆布包 免费</view>
						<view class="company one-line">郑州多喵咪帆布包装有限公司郑州多喵咪帆布包装有限公司</view>
						<view class="price-line">
							<view class="price">￥299.00</view>
							<view class="deal">成交56200元</view>
						</view>
					</view>
				</view>
			</view>
		</view>

		<view class="hr"></view>

		<!-- 爆款推荐 -->
		<view class="hot-box">
			<view class="title">
				<image src="../../static/icons/fire.png"></image>
				爆款推荐
			</view>
			<view class="product-list">
				<view class="product" v-for="i in num">
					<image src="../../static/t-images/goods.jpg" class="cover" mode="aspectFill" lazy-load></image>
					<view class="info">
						<view class="title two-line">{{i == 3 ? '民间工艺' : '民间工艺文创陶罐文物彩陶涡纹壶复制品摆件民间工艺文创陶罐文物彩陶涡纹壶复制品摆件'}}</view>
						<view class="company one-line">中国国家博物馆中国国家博物馆</view>
						<view class="price">￥299.00</view>
					</view>
				</view>
			</view>
			<uni-load-more :status="more"></uni-load-more>
		</view>
	</view>
</template>

<script>
	import uniLoadMore from "@/components/uni-load-more/uni-load-more.vue"

	export default {
		components: {
			uniLoadMore
		},
		data() {
			return {
				num: 5,
				more: 'more'
			}
		},
		onLoad() {
		},
		onPullDownRefresh() {
			uni.stopPullDownRefresh();
		},
		onReachBottom() {
			if (this.num > 40) {
				this.more = 'noMore';
			} else {
				this.more = 'loading';
				setTimeout(() => {
					this.more = 'more';
					this.num += 5;
				}, 300);
			}
		},
		methods: {}
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

	.swiper {
		height: 288rpx;

		swiper-item {
			image {
				width: 100%;
				height: 100%;
			}
		}
	}

	.kingkong {
		padding: 24rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;

		navigator {
			display: flex;
			flex-direction: column;
			align-items: center;
			margin-right: 30rpx;
			width: 96rpx;
			margin-top: 40rpx;

			&:nth-child(-n + 5) {
				margin-top: 0;
			}

			&:nth-child(5n) {
				margin-right: 0;
			}

			image {
				width: 80rpx;
				height: 80rpx;
			}

			.title {
				margin-top: 12rpx;
				color: #666;
				font-size: 24rpx;
				white-space: nowrap;
			}
		}
	}

	.video-box {
		padding: 39rpx 24rpx;

		.title-line {
			display: flex;
			align-items: flex-end;
			justify-content: space-between;
			padding-bottom: 24rpx;
			border-bottom: 2rpx solid rgba(0, 0, 0, 0.03);

			.title {
				font-size: 40rpx;
				color: #333;
			}

			.more {
				display: flex;
				align-items: center;
				font-size: 26rpx;
				color: #666;

				image {
					width: 13rpx;
					height: 23rpx;
					margin-left: 7rpx;
				}
			}
		}

		.video-list {
			padding-top: 24rpx;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;

			.video {
				margin-top: 39rpx;
				width: 339rpx;

				&:first-child {
					margin-top: 0;
					width: 100%;

					.cover-box {
						height: 395rpx;
					}
				}

				.cover-box {
					height: 191rpx;
					position: relative;
					border-radius: 10rpx;
					overflow: hidden;

					.cover {
						width: 100%;
						height: 100%;
						vertical-align: bottom;
					}

					.mask {
						position: absolute;
						left: 0;
						top: 0;
						width: 100%;
						height: 100%;
						z-index: 1;
						background: rgba(0, 0, 0, 0.5);
						border-radius: 8rpx;

						.play {
							position: absolute;
							background: rgba(0, 0, 0, 0.6);
							width: 80rpx;
							height: 80rpx;
							border-radius: 50%;
							left: 0;
							right: 0;
							bottom: 0;
							top: 0;
							margin: auto;

							&::after {
								content: '';
								width: 0;
								height: 0;
								border-width: 20rpx 30rpx;
								border-style: solid;
								border-color: transparent transparent transparent #fff;
								position: absolute;
								left: 30rpx;
								top: 20rpx;
								opacity: 0.8;
							}
						}
					}
				}

				.info {
					padding-top: 20rpx;

					.title {
						font-size: 28rpx;
						color: #333;
					}

					.price-and {
						margin-top: 20rpx;
						display: flex;
						justify-content: space-between;
						align-items: flex-end;

						.price {
							font-size: 34rpx;
							color: #ff4032;
						}

						.heart {
							width: 38rpx;
							height: 38rpx;
						}
					}
				}
			}
		}
	}

	.custom-box {
		padding: 39rpx 0;

		.title {
			text-align: center;
			font-size: 40rpx;
			color: #333;
		}

		.tabs {
			margin-top: 24rpx;
			padding: 29rpx 30rpx;
			display: flex;
			align-items: flex-end;
			justify-content: space-between;
			background: #fafafa;

			.tab {
				font-size: 28rpx;
				color: #333;
				width: 0;
				flex-grow: 1;
				text-align: center;

				&.active {
					font-size: 32rpx;
					position: relative;

					&::after {
						content: '';
						position: absolute;
						left: 0;
						right: 0;
						margin: auto;
						bottom: -29rpx;
						width: 40rpx;
						height: 5rpx;
						background: #ff8432;
						border-radius: 3rpx
					}
				}
			}
		}

		.product-list {
			padding: 24rpx 24rpx 0;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;

			.product {
				margin-top: 39rpx;
				width: 339rpx;

				&:nth-child(-n + 2) {
					margin-top: 0;
				}

				.cover {
					width: 339rpx;
					height: 226rpx;
					border-radius: 10rpx
				}

				.info {
					padding-top: 19rpx;

					.title {
						font-size: 28rpx;
						color: #333;
					}

					.company {
						margin-top: 16rpx;
						font-size: 24rpx;
						color: #999;
					}

					.price-line {
						margin-top: 29rpx;
						display: flex;
						align-items: flex-end;
						justify-content: space-between;

						.price {
							font-size: 34rpx;
							color: #ff4032;
						}

						.deal {
							font-size: 22rpx;
							color: #ccc;
						}
					}
				}
			}
		}
	}

	.hot-box {
		padding: 40rpx 24rpx 15rpx;

		&>.title {
			font-size: 40rpx;
			color: #333;
			padding-bottom: 25rpx;
			border-bottom: 2rpx solid rgba(0, 0, 0, 0.03);
			text-align: center;

			image {
				width: 40rpx;
				height: 40rpx;
				margin-right: 12rpx;
			}
		}

		.product-list {
			padding-top: 24rpx;
			padding-bottom: 15rpx;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;

			.product {
				margin-top: 24rpx;
				width: 339rpx;

				&:nth-child(-n + 2) {
					margin-top: 0;
				}

				.cover {
					width: 339rpx;
					height: 339rpx;
					border-radius: 10rpx 10rpx 0 0;
					vertical-align: bottom;
				}

				.info {
					padding: 13rpx 16rpx 19rpx;
					border: 2rpx solid #ccc;
					border-top-width: 0;
					border-radius: 0 0 10rpx 10rpx;

					.title {
						font-size: 28rpx;
						line-height: 42rpx;
						height: 84rpx;
						color: #333;
					}

					.company {
						margin-top: 10rpx;
						font-size: 24rpx;
						color: #999;
					}

					.price {
						margin-top: 25rpx;
						font-size: 34rpx;
						color: #ff4032;
					}
				}
			}
		}
	}

	/* -------- common -------- */
	.hr {
		height: 7rpx;
		background: #fafafa;
	}
</style>
