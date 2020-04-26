<template>
	<view class="product-list" :class="{sp: sidePadding}">
		<view class="product" v-for="i in num">
			<image src="../../static/t-images/goods.jpg" class="cover" mode="aspectFill" lazy-load></image>
			<view class="info">
				<view class="title two-line">{{i == 3 ? '民间工艺' : '民间工艺文创陶罐文物彩陶涡纹壶复制品摆件民间工艺文创陶罐文物彩陶涡纹壶复制品摆件'}}</view>
				<view class="company one-line">中国国家博物馆中国国家博物馆</view>
				<view class="price">￥299.00</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'

	export default {
		name: "ProductList",
		props: {
			// 两边是否有边距，默认true
			sidePadding: {
				type: Boolean,
				default: true
			},
			// 商品数量（假数据）
			num: {
				type: Number,
				default: 5
			}
		},
		data() {
			return {
			};
		},
		methods: {},
		components: {
			uniSearchBar
		}
	}
</script>

<style lang="scss">
	.product-list {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		
		&.sp {
			padding-left: 24rpx;
			padding-right: 24rpx;
		}

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
</style>
