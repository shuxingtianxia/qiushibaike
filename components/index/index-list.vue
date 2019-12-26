<template>
	<view class="list-box">
		<!-- 第一行 -->
		<view class="index-list1 u-flex u-f-jcs u-f-aic">
			<view class="head-left u-flex u-f-jcs u-f-aic">
				<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
				<text>你好</text>
			</view>
			<view class="head-right u-flex u-f-aic">
				<view class="icon iconfont icon-zengjia"></view>关注
			</view>
		</view>
		<!-- 第二行 -->
		<view class="index-list2">标题</view>
		<!-- 第三行 -->
		<view class="index-list3 u-flex u-f-jcc u-f-aic">
			<!-- 图片 -->
			<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
			<!-- 视频 -->
			<view class="icon iconfont icon-bofang icon-play"></view>
			<view class="plsy_num">20w次播放 2:47</view>
		</view>
		<!-- 第四行 -->
		<view class="index-list4 u-flex u-f-jcs u-f-aic">
			<view class="u-flex u-f-aic">
				<view class="u-flex u-f-aic">
					<view class="icon iconfont icon-icon_xiaolian-mian"></view>
					10
				</view>
				<view class="u-flex u-f-aic">
					<view class="icon iconfont icon-kulian"></view>
					10
				</view>
			</view>
			<view class="u-flex u-f-aic">
				<view class="u-flex u-f-aic">
					<view class="icon iconfont icon-pinglun1"></view>
					10
				</view>
				<view class="u-flex u-f-aic">
					<view class="icon iconfont icon-zhuanfa"></view>
					10
				</view>
			</view>
		</view>
	</view>
</template>

<script>
</script>

<style scoped lang="scss">
	.list-box {
		padding: 20upx;
		border-bottom: 1upx solid #EEEEEE;
	
		.index-list1 {
			.head-left {
				image {
					width: 85upx;
					height: 85upx;
					margin-right: 10upx;
					border-radius: 100%;
				}
	
				text {
					color: #999999;
				}
			}
	
			.head-right {
				background: #f4f4f4;
				border-radius: 5upx;
				padding: 0 10upx;
			}
		}
	
		.index-list2 {
			padding-top: 15upx;
			font-size: 32upx;
		}
	
		.index-list3 {
			position: relative;
			padding-top: 15upx;
	
			image {
				width: 100%;
				max-height: 450upx;
				border-radius: 20upx;
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
		}
	
		.index-list4 {
			color: #999999;
	
			view {
				margin: 0 10upx;
			}
		}
	}
</style>
