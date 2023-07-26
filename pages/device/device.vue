<template>
	<view>
		<!-- 监控画面 -->
		<view class="monitor">
			<image class="photo" src="/static/baby.png" mode="widthFix"></image>
		</view>
		<!-- 数据窗口 -->
		<view class="data">
			<view class="data-info">
				<view class="data-info-title">
					宝宝体温
				</view>
				<view class="data-info-num">
					36.3℃
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					宝宝心率
				</view>
				<view class="data-info-num">
					{{heart}}
					<view class="data-info-min">
						次/分钟
					</view>
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					环境温度
				</view>
				<view class="data-info-num">
					{{temp}}℃
				</view>
			</view>
			<view class="data-info">
				<view class="data-info-title">
					宝宝呼吸
				</view>
				<view class="data-info-num">
					42
					<view class="data-info-min">
						次/分钟
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				temp: 24.8,
				heart: 110,
			};
		},
		mounted() {
			this.temp = setInterval(() => {
				this.temp = this.getRandomTemp(24, 25);
			}, 10000)
			this.heart = setInterval(() => {
				this.heart = this.getRandomHeart(110, 120);
			}, 10000)
		
		},
		methods: {
			getRandomTemp(min, max) {
				return (Math.random() * (max - min) + min).toFixed(1);
				// console.log(this.temp);
			},
			getRandomHeart(min, max) {
				return (Math.random() * (max - min) + min).toFixed(0);
				// console.log(this.temp);
			},
		}
	}
</script>

<style lang="scss">
	.monitor {
		display: flex;
		width: 701rpx;
		height: 526rpx;
		margin-left: 24.5rpx;
		margin-top: 17.5rpx;
		border-radius: 43.8rpx;
		background-color: #FFF;
		overflow: hidden;

		.photo {
			width: 701rpx;
		}
	}

	.data {
		display: flex;
		flex-wrap: wrap;
		margin-left: 24.5rpx;


		.data-info {
			height: 333.33rpx;
			width: 333.33rpx;
			background-color: #FFF;
			border-radius: 17.54rpx;
			margin-top: 24.5rpx;
			margin-right: 26rpx;

			.data-info-title {
				margin-left: 28rpx;
				line-height: 71.1rpx;
				font-size: 12px;
				font-weight: 700;
				height: 71.1rpx;
			}

			.data-info-num {
				display: inline-block;
				margin-top: 187.7rpx;
				margin-left: 28rpx;
				margin-right: 2rpx;
				line-height: 73.7rpx;
				font-size: 30px;
				font-weight: 500;
				height: 73.7rpx;
				color: rgba(0, 0, 0, 0.5);

				.data-info-min {
					display: inline-block;
					font-size: 16px;
				}
			}
		}
	}
</style>
