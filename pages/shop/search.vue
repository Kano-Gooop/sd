<template>
	<view class="page">
		<!-- 头部搜索框 -->
		<view class="top">
			<uni-search-bar @confirm="search" cancelButton="none" :maxlength="30" bgColor="#fff" class="search"></uni-search-bar>
		</view>
		
		<!-- 商品列表 -->
		<product-list :num="num"></product-list>
		<uni-load-more :status="more"></uni-load-more>
	</view>
</template>

<script>
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'
	
	import productList from '@/my-components/product-list/index.vue'

	export default {
		data() {
			return {
				num: 5,
				more: 'more'
			};
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
		methods: {
			// 搜索商品
			search(e) {
				console.log('搜索了：', e.value)
			},
		},
		components: {
			uniSearchBar,
			productList
		}
	}
</script>

<style lang="scss">
	.page {
		padding-top: 104rpx;
		padding-bottom: 15rpx;

		.top {
			position: fixed;
			top: var(--window-top);
			width: 100%;
			z-index: 2;
			
			.search {
				background: #f5f5f5;
				
				/deep/ .uni-searchbar__box {
					border: none;
				}
			}
		}
		
		.product-list {
			margin-top: 24rpx;
			padding-bottom: 15rpx;
		}
	}
</style>
