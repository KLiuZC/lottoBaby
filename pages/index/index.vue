<template>
	<view class="content">
		<view class="healthState">
			<view class="back">
				<uni-icons type="back" size="14"></uni-icons>
			</view>
			<view class="healthTitle">
				宝宝健康状态
			</view>
			<view class="forward">
				<uni-icons type="forward" size="14"></uni-icons>
			</view>



			<view class="healthDetail">
				<view class="healthCapsule">
					<view class="whiteCircle">
						2
					</view>
					<view class="days">
						Mon
					</view>
				</view>
				<view class="healthCapsule yellow">
					<view class="whiteCircle">
						3
					</view>
					<view class="days">
						Tue
					</view>
				</view>
				<view class="healthCapsule">
					<view class="whiteCircle">
						4
					</view>
					<view class="days">
						Wed
					</view>
				</view>
				<view class="healthCapsule brown">
					<view class="whiteCircle">
						5
					</view>
					<view class="days">
						Thur
					</view>
				</view>
				<view class="healthCapsule">
					<view class="whiteCircle">
						6
					</view>
					<view class="days">
						Fri
					</view>
				</view>
				<view class="healthCapsule">
					<view class="whiteCircle">
						7
					</view>
					<view class="days">
						Sat
					</view>
				</view>
				<view class="healthCapsule">
					<view class="whiteCircle">
						8
					</view>
					<view class="days">
						Sun
					</view>
				</view>
			</view>

		</view>
		<view class="dataCurve">
			<view class="healthTitle">
				宝宝数据曲线
			</view>
			<view class="healthData">
				<qiun-data-charts type="line" :opts="opts" :chartData="chartData" />
			</view>
		</view>
		<!-- https://ext.dcloud.net.cn/plugin?id=1971 -->
		<view class="tabBar">
			<v-tabs v-model="activeTab" :scroll="false" :tabs="['热门','关注','知识','直播']" color="#0d0d0d"
				activeColor="#0d0d0d" lineColor="#e1c600" lineHeight="5.26rpx" height="60rpx" fontSize="18px"></v-tabs>
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
					<image class="newsCardImgContent" src="../../static/tiku.png" mode="widthFix"></image>
				</view>
				<view class="newsCardBg">
					<view class="newsCardTitle">
						孩子啼哭不止怎么办
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
							12
						</view>
					</view>
				</view>
			</view>

			<view class="newsCard">
				<view class="newsCardImg">
					<image class="newsCardImgContent" src="../../static/chahua.png" mode="widthFix"></image>
				</view>
				<view class="newsCardBg">
					<view class="newsCardTitle">
						第一届Lotto婴幼插画大赛
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
							3721
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import {
		onMounted
	} from "vue";
	export default {
		data() {
			return {
				activeTab: 0,
				temp: 0,
				timer: {
					year: null,
					month: null,
					date: null,
					hour: null,
					min: null,
					sec: null,
				},
				babyData: '',
				chartData: {},
				opts: {
					color: ["#1890FF", "#91CB74", "#FAC858", "#EE6666", "#73C0DE", "#3CA272", "#FC8452", "#9A60B4", "#ea7ccc"],
					padding: [15, 10, 0, 15],
					dataLabel: false,
					dataPointShape: false,
					enableScroll: false,
					legend: {},
					xAxis: {
						disableGrid: true
					},
					yAxis: {
						gridType: "dash",
						dashLength: 2,
						data: [{
							min: 35,
							max: 39
						}]
					},
					extra: {
						line: {
							type: "curve",
							width: 2,
							activeType: "hollow",
							linearType: "custom"
						}
					}
				}
			}
		},
		onLoad() {

		},
		onReady() {
		    this.getServerData();
		},
		mounted() {
			this.temp = setInterval(() => {
				this.temp = this.getRandomTemp(36, 37);
				this.timer.year = new Date().getFullYear();
				this.timer.month = new Date().getMonth();
				this.timer.date = new Date().getDate();
				this.timer.hour = new Date().getHours();
				this.timer.min = new Date().getMinutes();
				this.timer.sec = new Date().getSeconds();
				this.timer.hour = this.timer.hour < 10 ? '0' + this.timer.hour : this.timer.hour
				this.timer.min = this.timer.min < 10 ? '0' + this.timer.min : this.timer.min
				this.timer.sec = this.timer.sec < 10 ? '0' + this.timer.sec : this.timer.sec
			}, 1000)

		},
		methods: {
			getRandomTemp(min, max) {
				return (Math.random() * (max - min) + min).toFixed(1);
				// console.log(this.temp);
			},
			getServerData() {
			  //模拟从服务器获取数据时的延时
			  setTimeout(() => {
			    //模拟服务器返回数据，如果数据格式和标准格式不同，需自行按下面的格式拼接
			    let res = {
			        categories: ["8:00","8:10","8:20","8:30","8:40","8:50"],
			        series: [
			          {
			            name: "体温",
			            linearColor: [
			              [
			                0,
			                "#1890FF"
			              ],
			              [
			                0.25,
			                "#00B5FF"
			              ],
			              [
			                0.5,
			                "#00D1ED"
			              ],
			              [
			                0.75,
			                "#00E6BB"
			              ],
			              [
			                1,
			                "#90F489"
			              ]
			            ],
			            data: [36.1,37.3,36.1,37.3,36.1,37.3]
			          },
			          // {
			          //   name: "成交量B",
			          //   linearColor: [
			          //     [
			          //       0,
			          //       "#91CB74"
			          //     ],
			          //     [
			          //       0.25,
			          //       "#2BDCA8"
			          //     ],
			          //     [
			          //       0.5,
			          //       "#2AE3A0"
			          //     ],
			          //     [
			          //       0.75,
			          //       "#C4D06E"
			          //     ],
			          //     [
			          //       1,
			          //       "#F2D375"
			          //     ]
			          //   ],
			          //   data: [55,85,55,85,55,85]
			          // },
			          // {
			          //   name: "成交量C",
			          //   linearColor: [
			          //     [
			          //       0,
			          //       "#FAC858"
			          //     ],
			          //     [
			          //       0.33,
			          //       "#FFC371"
			          //     ],
			          //     [
			          //       0.66,
			          //       "#FFC2B2"
			          //     ],
			          //     [
			          //       1,
			          //       "#FA7D8D"
			          //     ]
			          //   ],
			          //   data: [95,125,95,125,95,125]
			          // }
			        ]
			      };
			    this.chartData = JSON.parse(JSON.stringify(res));
			  }, 500);
			},
		},

		beforeDestroy() { // 在销毁之前前生命周期 消除定时器
			clearInterval(this.temp);
			this.temp = 0;
			this.timer = null;
		},

	}
</script>

<style lang="scss">
	.healthState {
		width: 701rpx;
		height: 193rpx;
		margin-left: 24.5rpx;
		margin-top: 31.6rpx;
		border-radius: 35rpx;
		background-color: #fff;

		.back {
			float: left;
			margin-left: 16rpx;
			margin-top: 19.8rpx;
			font-weight: 700;
		}

		.forward {
			float: right;
			margin-right: 16rpx;
			margin-top: 19.8rpx;
			font-weight: 700;
		}

		.healthTitle {
			display: inline-block;
			margin-left: 250rpx;
			margin-top: 19.3rpx;
			font-size: 13px;
			font-weight: 700;
		}

		.healthDetail {
			.healthCapsule {
				width: 52.88rpx;
				height: 101.56rpx;
				background-color: #00E1D4;
				border-radius: 35rpx;
				// margin-left: 40.68rpx;
				margin-right: 41rpx;
				margin-top: 17rpx;
				box-shadow: 0rpx 7rpx 7rpx rgba(0, 0, 0, 0.25);
				overflow: hidden;
				display: inline-block;

				.whiteCircle {
					width: 40.7rpx;
					height: 40.7rpx;
					background-color: #fff;
					border-radius: 50%;
					margin-top: 10.16rpx;
					margin-left: 5.96rpx;
					font-size: 10px;
					display: flex;
					align-items: center;
					justify-content: center;
				}

				.days {
					font-size: 8px;
					color: #fff;
					display: flex;
					// align-items: center;
					margin-top: 16.25rpx;
					justify-content: center;
				}
			}

			.yellow {
				background-color: #CBB300;
			}

			.brown {
				background-color: #9E5F00;
			}
		}

		.healthDetail .healthCapsule:last-child {
			margin-right: 0;
		}
	}

	.dataCurve {
		width: 701rpx;
		height: 284.21rpx;
		margin-left: 24.5rpx;
		margin-top: 35rpx;
		border-radius: 43.86rpx;
		background-color: #fff;

		.healthTitle {
			display: inline-block;
			margin-left: 287.72rpx;
			margin-top: 19.3rpx;
			font-size: 13px;
			font-weight: 700;
		}

		.healthData {
			// text-align: center;
			width: 100%;
			height: 240rpx;
		}
	}

	.tabBar {
		width: 701rpx;
		height: 70.175rpx;
		margin-left: 24.5rpx;
		margin-top: 35rpx;
		border-radius: 43.86rpx;
		background-color: #fff;


		.v-tabs {
			border-radius: 43.86rpx;

		}
	}


	.news {
		// display: flex;
		// flex-wrap: wrap;
		// flex-direction: row;
		// justify-content: space-between;
		// align-items: flex-start;
		// align-content: space-between;
		column-count: 2;

		margin-left: 24.5rpx;
		margin-right: 24.5rpx;
		margin-top: 19.3rpx;

		.newsCard {
			display: inline-block;
			margin-bottom: 36rpx;

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
