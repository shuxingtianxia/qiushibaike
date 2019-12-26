<template>
	<view class="topic-list u-flex">
		<view class="topic-left">
			<image src="../../static/logo.png" mode="widthFix" lazy-load=""></image>
		</view>
		<view class="topic-right">
			<view class="topic-name">#话题名称#</view>
			<view class="topic-decs">我是话题描述</view>
			<view>动态 50 今日 10</view>
		</view>
	</view>


</template>

<script>
</script>

<style scoped lang="scss">
.topic-list{
	padding: 10px 0;
	border-bottom: 1upx solid #EEEEEE;
	.topic-left{
		image{
			width: 150upx;
			height: 150upx;
			border-radius: 10upx;
			margin-right: 20upx;
		}
	}
	.topic-right{
		color: #a4a4a4;
		.topic-name{
			color: #333333;
			font-size: 32upx;
		}
	}
}
</style>
