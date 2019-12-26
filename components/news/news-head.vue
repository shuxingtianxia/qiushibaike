<template>
	<uni-nav-bar :fixed="true" left-icon="back">
		<block slot="left">
			<view class="nav-left">
				<view class="icon iconfont icon-qiandao"></view>
			</view>
		</block>
		<!-- 中间 -->
		<view class="nav-center u-flex u-f-jcc u-f-aic">
			<block v-for="(tab,index) in tabBars" :key="tab.id">
				<view class="u-flex u-f-jcc u-f-aic" 
				:class="{'active':tabIndex==index}" 
				@tap="changeTab(index)">
					{{tab.name}}
					<view v-if="(tabIndex==index)" class="nav-tab-bar-line"></view>
				</view>
			</block>
		</view>
		<!-- 右边 -->
		<block slot="right">
			<view class="nav-right u-flex" @tap="tabtap">
				<view class="icon iconfont icon-bianji1"></view>
			</view>
		</block>
	</uni-nav-bar>
</template>

<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue";
	export default{
		components:{
			uniNavBar
		},
		props:{
			tabBars:Array,
			tabIndex:Number
		},
		methods: {
			changeTab(index) {
				this.$emit('change-tab', index)
			},
			tabtap() {
				uni.navigateTo({
					url: '/pages/send-msg/send-msg'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
	.nav-left{
		margin-left: 20upx;
		.icon-qiandao{
			font-size: 40upx;
			color: #FF9619;
		}
	}
	.nav-center{
		position: relative;
		width: 100%;
		view{
			font-size: 32upx;
			color:#969696;
			font-weight: 700;
			&.active{
				color: #333;
			}
		}
		view:first-child{
			margin-right: 50upx;
		}
		.nav-tab-bar-line{
			border-bottom: 4upx solid #FEDE33;
			border-top: 4upx solid #FEDE33;
			width: 70upx;
			border-radius: 20upx;
			position: absolute;
			bottom: 0;
			
		}
	}
	.nav-right{
		margin-right: 20upx;
		.icon-bianji1{
			font-size: 40upx;
		}
	}
</style>
