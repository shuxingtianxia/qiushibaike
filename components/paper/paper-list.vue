<template>
	<view class="u-flex u-f-jcs paper-list">
		<image class="avatar"  src="../../static/logo.png" mode=""></image>
		<view>
			<view class="username u-flex u-f-jcs">
				名字
				<view>10:20</view>
			</view>
			<view class="content u-flex u-f-jcs">
				我是内容
				<uniBadge text="2"	type="error">s</uniBadge>
			</view>
		</view>
		
	</view>
	
</template>

<script>
	import uniBadge from "@/components/uni-badge/uni-badge.vue"
	export default {
	    components: {uniBadge}
	}
</script>

<style scoped lang="scss">
	.paper-list{
		padding: 20upx 0;
		border-bottom: 1upx solid #EEEEEE;
		.avatar{
			width: 100upx;
			height: 100upx;
			border-radius: 50%;
			margin-right: 20upx;
		}
		&>view{
			flex: 1;
		}
		.username{
			font-size: 35upx;
			view{
				color: #CBCBCB;
			}
		}
		.content{
			color: #999999;
		}
	}
	
</style>
