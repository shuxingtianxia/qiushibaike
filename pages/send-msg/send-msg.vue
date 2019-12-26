<template>
	<view>
		<view class="head u-flex u-f-jcs u-f-aic">
			<view class="icon iconfont icon-fanhui" @tap="back"></view>
			<view class="look" @tap="look">{{lookMsg}}<text class="icon iconfont icon-xialazhankai"></text></view>
			<view class="send" @tap="publish">发布</view>
		</view>
		<view  class="uni-textarea">
			<textarea value="" placeholder="" />
		</view>
		<view class="uni-list list-pd">
			<view class="uni-list-cell cell-pd">
				<view class="uni-uploader">
					<view class="uni-uploader-head">
						<view class="uni-uploader-title">点击可预览选好的图片</view>
						<view class="uni-uploader-info">{{imageList.length}}/9</view>
					</view>
					<view class="uni-uploader-body">
						<view class="uni-uploader__files">
							<block v-for="(image,index) in imageList" :key="index">
								<view class="uni-uploader__file">
									<image class="uni-uploader__img" :src="image" :data-src="image" @tap="previewImage"></image>
								</view>
							</block>
							<view class="uni-uploader__input-box">
								<view class="uni-uploader__input" @tap="chooseImage"></view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 广告层 -->
		<uni-popup ref="showpopup" :type="type">
			<view class="adv">
				<view class="u-flex u-f-aic u-f-jcc">
					<image src="../../static/common/addinput.png" mode="widthFix"></image>
				</view>
				<view>1.涉及黄色，政治，广告及骚扰信息</view>
				<view>2.涉及黄色，政治，广告及骚扰信息</view>
				<view>3.涉及黄色，政治，广告及骚扰信息</view>
				<view>4.涉及黄色，政治，广告及骚扰信息</view>
				<button type="default" @tap="hidePopup">朕知道了</button>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	import uniPopup from '@/components/uni-popup/uni-popup.vue'
	var sourceType = [
		['camera'],
		['album'],
		['camera', 'album']
	]
	var sizeType = [
		['compressed'],
		['original'],
		['compressed', 'original']
	]
	// import permision from "@/common/permission.js"
	export default {
		components: {
			uniPopup
		},
		data() {
			return {
				imageList: [],
				sourceTypeIndex: 2,
				sourceType: ['拍照', '相册', '拍照或相册'],
				sizeTypeIndex: 2,
				sizeType: ['压缩', '原图', '压缩或原图'],
				countIndex: 8,
				count: [1, 2, 3, 4, 5, 6, 7, 8, 9],
				type: 'center',
				changelook: ['所有人都可见', '仅自己可见'],
				lookMsg: '所有人都可见'
			}
		},
		mounted() {
			this.$nextTick(() => {
				this.$refs['showpopup'].open()
			})
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
			},
			// 隐藏广告
			hidePopup() {
				this.$refs['showpopup'].close()
			},
			chooseImage: async function() {
				// #ifdef APP-PLUS
				// TODO 选择相机或相册时 需要弹出actionsheet，目前无法获得是相机还是相册，在失败回调中处理
				if (this.sourceTypeIndex !== 2) {
					let status = await this.checkPermission();
					if (status !== 1) {
						return;
					}
				}
				// #endif
			
				if (this.imageList.length === 9) {
					let isContinue = await this.isFullImg();
					console.log("是否继续?", isContinue);
					if (!isContinue) {
						return;
					}
				}
				uni.chooseImage({
					sourceType: sourceType[this.sourceTypeIndex],
					sizeType: sizeType[this.sizeTypeIndex],
					count: this.imageList.length + this.count[this.countIndex] > 9 ? 9 - this.imageList.length : this.count[this.countIndex],
					success: (res) => {
						this.imageList = this.imageList.concat(res.tempFilePaths);
					}
				})
			},
			// 上传图片
			previewImage: function(e) {
				var current = e.target.dataset.src
				uni.previewImage({
					current: current,
					urls: this.imageList
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
.uni-textarea{
	border: 1upx solid #EEEEEE;
}
.list-pd{
	margin-top: 20upx;
}
.cell-pd {
	padding: 22upx 30upx;
}
	
// 广告框
.adv {
	width: 500upx;
	background-color: #fff;
	padding: 15px;
	font-size: 14px;
	border-radius: 10upx;
	image{
		width: 75%;
		margin-bottom: 20upx;
	}
	button{
		margin-top: 20upx;
		background: #FFE934;
		color: #171606;
	}
}
</style>
