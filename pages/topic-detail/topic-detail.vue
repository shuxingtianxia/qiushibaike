<template>
	<view class="topic">
		<!-- 模糊背景 -->
		<view class="topic-bg">
			<image mode="aspectFill" src="../../static/common/1.jpg"></image>
			<!-- 返回按钮 -->
			<view class='top-back u-flex u-f-jcs'>
				<view class="icon-fl"><text class="icon iconfont icon-fanhui"></text></view>
				<view class="icon-fr"><text class="icon iconfont icon-gengduo1"></text></view>
			</view>
		</view>
		<!-- 话题信息 -->
		<view class="topic-info">
			<view class="topic-info-title">
				<image src="../../static/common/1.jpg" mode="aspectFill"></image>
				<view>#一回忆，就伤感#</view>
			</view>
			<view class="topic-info-num u-flex">
				<view><text>动态</text><text>1000</text></view>
				<view><text>今日</text><text>1000</text></view>
			</view>
			<view class="topic-info-desc">我是描述</view>
		</view>
		<!-- 导航 -->
		<swiper-tab-head 
			:tabIndex='tabIndex'
			@tabtap='tabtap'
			:navList='navList'
			scrollItemStyle='width: 50%'
		></swiper-tab-head>
		<common-list></common-list>
	</view>
</template>

<script>
	import swiperTabHead from '@/components/common/swiper-tab-head.vue'
	import commonList from '@/components/common/common-list.vue'
	export default{
		data() {
			return{
				tabIndex: 0,
				navList: ['默认', '最新']
			}
		},
		components: {
			swiperTabHead,
			commonList
		},
		methods: {
			// 点解导航栏切换
			tabtap(index) {
				this.tabIndex = index
				this.current = index
			},
		}
	}
</script>

<style scoped lang="scss">
	.topic{
		// 背景图
		.topic-bg{
			position: relative;
			width: 100%;
			height: 300upx;
			overflow: hidden;
			image{
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				filter: blur(10px); // 图片模糊
			}
			.top-back{
				position: absolute;
				top: 10upx;
				width: 100%;
				
				.icon-fl{
					margin-left: 10upx;
				}
				.icon-fr{
					margin-right: 10upx;
				}
				&>view{
					display: flex;
					align-items: center;
					justify-content: center;
					width: 64upx;
					height: 64upx;
					border-radius: 50%;
					background: rgba(0,0,0,.5);
					.icon{
						color: #FFFFFF;
					}
					.icon-fanhui{
						font-size: 38upx;
					}
				}
			}
		}
		.topic-info{
			padding: 0 25upx;
			.topic-info-title{
				position: relative;
				image{
					position: absolute;
					top: -75upx;
					left: 0;
					width: 150upx;
					height: 150upx;
					border-radius: 10upx;
				}
				view{
					font-size: 34upx;
					margin-left: 170upx;
				}
			}
		}
		.topic-info-num{
			padding: 34upx 0 14upx 0;
			color: #CDCDCD;
			view{
				margin-right: 30upx;
				text{
					margin-right: 10upx;
				}
			}
		}
	}
	
</style>
