<template>
	<view>
		<!-- 轮播图区域 -->
		<view class="banner">
			<uni-swiper-dot :info="info" :current="current" :mode="mode" calss="uni-swiper-dot-box" :dots-styles="dotStyles">
				<swiper class="swiper-box" :autoplay="true" :interval="3000" :duration="1000" :circular="true"
					@change="change">
					<swiper-item v-for="(item, index) in info" :key="index">
						<view class="swiper-item">
							<image :src="item.url" ></image>
						</view>
					</swiper-item>
				</swiper>
			</uni-swiper-dot>
		</view>
		
		<!-- 卡片区域 -->
		<view class="data">
			<view class="data-info">
				<view class="data-info-title">
					母婴商城
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/shanchen.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					早期教学
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/jiaoxue.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					妈妈论坛
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/luntan.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					专家问诊
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/zhuanjia.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					直播
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/zhibo.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					二手市场
				</view>
				<view class="data-info-pic">
					<image src="../../static/find-icon/ersou.png" mode="heightFix" style="height: 225rpx;"></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				info: [{
					url: '/static/banner.png'
				}, {
					url: '/static/banner.png'
				}, {
					url: '/static/banner.png'
				}, {
					url: '/static/banner.png'
				}, {
					url: '/static/banner.png'
				}],
				current: 0,
				mode: 'dot',
				dotStyles: {
					backgroundColor : '#fff',
					border: '1px solid #E1C600',
					selectedBackgroundColor : '#E1C600',
					selectedBorder: '1px solid #E1C600',
				},
			};
		},

		methods: {
			change(e) {
				this.current = e.detail.current;
			}
		}
	}
</script>

<style lang="scss">
	.banner {
		height: 526.31rpx;
		width: 701.75rpx;
		background-color: #fff;
		margin-top: 17.54rpx;
		margin-left: 24.56rpx;
		border-radius: 43.86rpx;
		overflow: hidden;
		
		.swiper-box {
			height: 526.31rpx;

			.swiper-item,
			image {
				height: 100%;
				width: 100%;
				// border-radius: 43.86rpx;
			}
		}
	}
	
	.data {
		display: flex;
		flex-wrap: wrap;
		margin-left: 24.5rpx;
	
	
		.data-info {
			height: 298.25rpx;
			width: 333.33rpx;
			background-color: #FFF;
			border-radius: 17.54rpx;
			margin-top: 35.09rpx;
			margin-right: 26rpx;
	
			.data-info-title {
				margin-left: 28rpx;
				line-height: 71.1rpx;
				font-size: 12px;
				font-weight: 700;
				height: 71.1rpx;
			}
			
			.data-info-pic{
				text-align: center;
			}
		}
	}
</style>
