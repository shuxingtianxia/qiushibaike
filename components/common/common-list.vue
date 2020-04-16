<template>
	<view class="common-list u-flex u-f-jcs">
		<view class="common-fl"><image src="../../static/common/addinput.png" mode="widthFix" lazy-load></image></view>
		<view class="common-fr">
			<view class="u-flex u-f-jcs u-f-aic">
				<view class="u-flex u-f-jcs u-f-aic">
					<text class="name">哈哈哈</text>
					<view class="tag-sex icon iconfont icon-nan">25</view>
				</view>
				<view class="icon iconfont icon-zengjia">
					关注
				</view>
			</view>
			<view class="common-content">
				<view>我是标题啊</view>
			</view>
			<view class="common-info u-flex u-f-jcc u-f-aic">
				<!-- 图片 -->
				<!-- <image src="../../static/logo.png" mode="widthFix" lazy-load></image> -->
				<!-- 视频 -->
				<!-- <template>
					<view class="icon-play icon iconfont icon-bofang">
					</view>
					<view class="plsy_num">
						20w 次播放 2:47
					</view>
				</template> -->
				<!-- 分享 -->
				<view class="common-list-share u-flex u-f-aic">
					<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
					<view>我是分享的标题</view>
				</view>
			</view>
			<view class="commnt-last u-flex u-f-aic u-f-jcs">
				<view>深圳 龙岗</view>
				<view class="goods u-flex u-f-aic">
					<view class="icon iconfont icon-zhuanfa">20</view>
					<view class="icon iconfont icon-pinglun1">30</view>
					<view class="icon iconfont icon-dianzan1">20</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
</script>

<style scoped lang="scss">
	.common-list{
		padding: 20upx;
		.common-fl{
			image{
				width: 90upx;
				border-radius: 100%;
			}
		}
		.common-fr{
			margin-left: 14upx;
			padding: 2upx;
			flex: 1;
			border-bottom: 1px solid #eee;
			.name{
				color:#999999;
				font-size: 32upx;;
			}
			.icon-zengjia{
				background: #EEEEEE;
				padding: 0 10upx;
				font-size: 26upx;
			}
			.tag-sex{
				background: #007AFF;
				font-size: 23upx;
				padding: 5upx 10upx;
				margin-left: 10upx;
				border-radius: 20upx;
				line-height: 22upx;
				color:#FFFFFF;
			}
			.common-content{
				font-size: 32upx;
				padding: 12upx 0;
			}
			.common-info{
				position: relative;
				width: 100%;
				image{
					width: 100%;
					max-height: 340upx;
					border-radius: 10upx;
				}
				.icon-play {
					position: absolute;
					font-size: 140upx;
					color: #FFFFFF;
				}
					
				.plsy_num {
					position: absolute;
					bottom: 8upx;
					right: 8upx;
					padding: 5upx 20upx;
					border-radius: 40upx;
					font-size: 22upx;
					background: rgba(51, 51, 51, 0.72);
					color: rgba(255, 255, 255, 0.8);
				}
				.common-list-share{
					width: 100%;
					background: #EEEEEE;
					padding: 10upx;
					border-radius: 10upx;
					font-size: 28upx;
					image{
						width: 200upx;
						margin-right: 10upx;
					}
				}
			}
			.commnt-last{
				margin-top: 10upx;
				padding-bottom: 5upx;
				color:#aaa;
				.goods{
					color:#aaa;
					view{
						margin-right: 10upx;
						font-size: 26upx;
					}
				}
			}
		}
	}
</style>
