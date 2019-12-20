<template>
	<view>
		<view class="head u-flex u-f-jc u-f-aj">
			<view class="icon iconfont icon-fanhui" @tap="back"></view>
			<view class="look" @tap="look">{{lookMsg}}<text class="icon iconfont icon-xialazhankai"></text></view>
			<view class="send" @tap="publish">发布</view>
		</view>
		<uni-popup msg="" :show="true" type="middle"></uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				changelook: ['所有人都可见', '仅自己可见'],
				lookMsg: '所有人都可见'
			}
		},
		methods: {
			// 返回上一层
			back() {
				uni.navigateBack({
					delta: 1
				})
			},
			// 发布
			publish() {
				console.log('发布')
			},
			// 谁可以查看
			look() {
				uni.showActionSheet({
					itemList: this.changelook,
					success: (res) => {
						this.lookMsg = this.changelook[res.tapIndex]
					}
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.head{
	height: 100upx;
	padding: 0 20upx;
	line-height: 100upx;
	border-bottom: 1upx solid #eee;
	.icon-fanhui{
		font-weight: 700;
		font-size: 34upx;
	}
	.look{
		color:#333333;
	}
	.send{
		font-size: 32upx;
		font-weight: 700;
		color: #333;
	}
}
</style>
