<template>
	<view>
		<view class="userCard">
			<view class="userAvatar">
				<image src="../../static/LOGO2.png" mode="widthFix"></image>
			</view>
			<view class="userInfo">
				<view class="firstLine">
					<view class="userName">
						LOTTO婴幼
					</view>
					<view class="personalInfo">
						个人信息
						<uni-icons type="forward" size="10"></uni-icons>
					</view>
				</view>

				<view class="secondLine">
					<view class="ipDependency">
						IP：广东
					</view>
					<view class="uidNum">
						UID：000000001
					</view>
				</view>

				<view class="thirdLine">
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
					<view class="grayCircle"></view>
				</view>

				<view class="forthLine">
					<view class="infoNum">
						关注：1
					</view>
					<view class="infoNum">
						粉丝：1
					</view>
					<view class="infoNum">
						点赞：1
					</view>
				</view>
			</view>
		</view>

		<view class="functionCard">
			<view class="functionCardBackground">
				<image src="../../static/tabler-icon/tabler-icon-pencil.png" mode="widthFix" class="tablerIcon"></image>
				<view class="tablerName">
					创作空间
				</view>
			</view>

			<view class="functionCardBackground">
				<image src="../../static/tabler-icon/tabler-icon-report-money.png" mode="widthFix" class="tablerIcon">
				</image>
				<view class="tablerName">
					红包卡券
				</view>
			</view>

			<view class="functionCardBackground">
				<image src="../../static/tabler-icon/tabler-icon-shopping-cart.png" mode="widthFix" class="tablerIcon">
				</image>
				<view class="tablerName">
					购物车
				</view>
			</view>

			<view class="functionCardBackground">
				<image src="../../static/tabler-icon/tabler-icon-star.png" mode="widthFix" class="tablerIcon"></image>
				<view class="tablerName">
					收藏
				</view>
			</view>
		</view>

		<!-- https://ext.dcloud.net.cn/plugin?id=1971 -->
		<view class="tabBar">
			<v-tabs v-model="activeTab" :scroll="false" :tabs="['圈子','记录','活动']" color="#0d0d0d" activeColor="#0d0d0d"
				lineColor="#e1c600" lineHeight="5.26rpx" height="60rpx" fontSize="18px"></v-tabs>
		</view>

		<view class="news">
			<view class="newsCard">
				<view class="newsCardImg">
					<image class="newsCardImgContent" src="../../static/yunqi.png" mode="widthFix"></image>
				</view>
				<view class="newsCardBg">
					<view class="newsCardTitle">
						孕前期大小事！
					</view>
					<view class="newsCardUser">

						<view class="newsCardLogo">
							<image style="width: 43.85rpx;" src="/static/lotto-logo.png" mode="widthFix"></image>
						</view>
						<view class="newsCardName">
							Lotto婴幼官方
						</view>
						<view class="newsCardLike">
							<image style="width: 29rpx;" src="/static/like.png" mode="widthFix"></image>
						</view>
						<view class="newsCardLikeNum">
							1387
						</view>
					</view>
				</view>
			</view>

			<view class="newsCard">
				<view class="newsCardImg">
					<image class="newsCardImgContent" src="../../static/jinyan.png" mode="widthFix"></image>
				</view>
				<view class="newsCardBg">
					<view class="newsCardTitle">
						育婴经验分享第一期
					</view>
					<view class="newsCardUser">

						<view class="newsCardLogo">
							<image style="width: 43.85rpx;" src="/static/lotto-logo.png" mode="widthFix"></image>
						</view>
						<view class="newsCardName">
							Lotto婴幼官方
						</view>
						<view class="newsCardLike">
							<image style="width: 29rpx;" src="/static/like.png" mode="widthFix"></image>
						</view>
						<view class="newsCardLikeNum">
							7387
						</view>
					</view>
				</view>
			</view>

			<view class="newsCard">
				<view class="newsCardImg">
					<image class="newsCardImgContent" src="../../static/duanlian.png" mode="widthFix"></image>
				</view>
				<view class="newsCardBg">
					<view class="newsCardTitle">
						孕前期瑜伽锻炼
					</view>
					<view class="newsCardUser">
						<view class="newsCardLogo">
							<image style="width: 43.85rpx;" src="/static/lotto-logo.png" mode="widthFix"></image>
						</view>
						<view class="newsCardName">
							Lotto婴幼官方
						</view>
						<view class="newsCardLike">
							<image style="width: 29rpx;" src="/static/like.png" mode="widthFix"></image>
						</view>
						<view class="newsCardLikeNum">
							36121
						</view>
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
				activeTab: 0
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.userCard {
		margin-top: 35.09rpx;
		margin-left: 31.58rpx;


		.userAvatar {
			height: 175.44rpx;
			width: 175.44rpx;
			border-radius: 50%;
			background-color: #D9D9D9;
			overflow: hidden;
			display: inline-block;
		}

		.userAvatar image {
			width: 176rpx;
		}

		.userInfo {
			color: #0D0D0D;
			margin-left: 38.6rpx;
			display: inline-block;
			vertical-align: top;

			.firstLine {
				.userName {
					font-weight: 500;
					font-size: 16px;
					letter-spacing: 0.1em;
					display: inline-block;
				}

				.personalInfo {
					margin-left: 187.72rpx;
					font-size: 10px;
					letter-spacing: 0.1em;
					display: inline-block;
					vertical-align: top;
				}
			}

			.secondLine {

				.ipDependency {
					font-size: 10px;
					letter-spacing: 0.1em;
					display: inline-block;
				}

				.uidNum {
					margin-left: 65rpx;
					font-size: 10px;
					letter-spacing: 0.1em;
					display: inline-block;
				}

			}

			.thirdLine {
				margin-top: 20rpx;

				.grayCircle {
					height: 38.6rpx;
					width: 38.6rpx;
					border-radius: 50%;
					background-color: #D9D9D9;
					margin-right: 10.53rpx;
					display: inline-block;
				}
			}

			.forthLine {
				.infoNum {
					margin-right: 77.2rpx;
					font-size: 12px;
					letter-spacing: 0.1em;
					display: inline-block;
				}

				.infoNum:last-child {
					margin-right: 0;
				}
			}
		}
	}

	.functionCard {
		margin-left: 49.12rpx;
		margin-top: 61.4rpx;

		.functionCardBackground {
			height: 140.35rpx;
			width: 140.35rpx;
			background-color: #fff;
			border-radius: 17.54rpx;
			box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.25);
			text-align: center;
			margin-right: 29.8rpx;
			display: inline-block;

			.tablerIcon {
				width: 42.1rpx;
				margin-top: 35rpx;
			}

			.tablerName {
				font-size: 21rpx;
				letter-spacing: 0.1em;
			}
		}

		.functionCardBackground:last-child {
			margin-right: 0;
		}
	}

	.tabBar {
		width: 701rpx;
		height: 70.175rpx;
		margin-left: 24.5rpx;
		margin-top: 35rpx;
		border-radius: 17.54rpx;
		background-color: #fff;
		box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.25);


		.v-tabs {
			border-radius: 17.54rpx;
		}
	}

	.news {
		column-count: 2;
		margin-left: 24.5rpx;
		margin-right: 24.5rpx;
		margin-top: 35rpx;

		.newsCard {
			display: inline-block;
			margin-bottom: 34.21rpx;

			.newsCardImg {
				.newsCardImgContent {
					width: 333.33rpx;
					vertical-align: top;
					border-radius: 26.31rpx 26.31rpx 0 0;
				}
			}

			.newsCardBg {
				width: 333.33rpx;
				background-color: #fff;
				// margin-left: 24.5rpx;
				border-radius: 0 0 26.31rpx 26.31rpx;
				overflow: hidden;

				.newsCardTitle {
					color: #000;
					letter-spacing: 0.05em;
					font-size: 12px;
					margin-top: 12.28rpx;
					margin-left: 15.79rpx;
				}

				.newsCardUser {
					display: flex;

					.newsCardLogo {
						width: 43.85rpx;
						height: 43.85rpx;
						margin-left: 15.79rpx;
						margin-top: 7rpx;
					}

					.newsCardName {
						margin-top: 14rpx;
						font-size: 10px;
						letter-spacing: 0.05em;
					}

					.newsCardLike {
						margin-left: 55rpx;
						margin-top: 12rpx;
					}

					.newsCardLikeNum {
						width: 36.84rpx;
						font-size: 10px;
						margin-left: 5rpx;
						margin-top: 17rpx;
						text-align: center;
					}
				}
			}
		}
	}
</style>
