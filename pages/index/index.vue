<template>
	<view>
		<view class="list-box">
			<!-- 第一行 -->
			<view class="index-list1 u-flex u-f-jc u-f-aj">
				<view class="head-left u-flex u-f-jc u-f-aj">
					<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
					<text>你好</text>
				</view>
				<view class="head-right u-flex u-f-aj">
					<view class="icon iconfont icon-zengjia"></view>关注
				</view>
			</view>
			<!-- 第二行 -->
			<view class="index-list2">标题</view>
			<!-- 第三行 -->
			<view class="index-list3">
				<image src="../../static/logo.png" mode="widthFix" lazy-load></image>
			</view>
			<!-- 第四行 -->
			<view class="index-list4 u-flex u-f-jc u-f-aj">
				<view class="u-flex u-f-aj">
					<view class="u-flex u-f-aj">
						<view class="icon iconfont icon-icon_xiaolian-mian"></view>
						10
					</view>
					<view class="u-flex u-f-aj">
						<view class="icon iconfont icon-kulian"></view>
						10
					</view>
				</view>
				<view class="u-flex u-f-aj">
					<view class="u-flex u-f-aj">
						<view class="icon iconfont icon-pinglun1"></view>
						10
					</view>
					<view class="u-flex u-f-aj">
						<view class="icon iconfont icon-zhuanfa"></view>
						10
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
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.list-box{
		padding: 20upx;
		border-bottom: 1upx solid #EEEEEE;
		.index-list1{
			.head-left{
				image{
					width: 85upx;
					height: 85upx;
					margin-right: 10upx;
					border-radius: 100%;
				}
				text{
					color: #999999;
				}
			}
			.head-right{
				background: #f4f4f4;
				border-radius: 5upx;
				padding: 0 10upx;
			}
		}
		.index-list2{
			padding-top: 15upx;
			font-size: 32upx;
		}
		.index-list3{
			position: relative;
			padding-top: 15upx;
			image{
				width: 100%;
				max-height: 550upx;
				border-radius: 20upx;
			}
		}
		.index-list4{
			color: #999999;
			view{
				margin: 0 10upx;
			}
		}
	}
</style>
