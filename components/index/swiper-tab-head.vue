<template>
	<view class="uni-tab-bar">
		<scroll-view class="uni-swiper-tab" :scroll-x="true" :show-scrollbar="false" >
			<view v-for="(tab,index) in 9" :key="tab.id" class="swiper-tab-list" :class="tabIndex == index ? 'active' : ''" :data-current="index" @click="ontabtap(index)">
				{{tab}}
				<view class="swiper-tab-line"></view>
			</view>
			
		</scroll-view>
	</view>
</template>

<script>
	export default{
		props: {
			tabIndex: Number,
		},
		data() {
			return{
				
			}
		},
		methods: {
			ontabtap(index) {
				this.$emit('tabtap', index)
			}
		}
	}
</script>

<style scoped lang="scss">
	.uni-tab-bar{
		.uni-swiper-tab{
			.swiper-tab-list{
				color: #969696;
				font-weight: bold;
			}
			.active{
				color: #343434;
				.swiper-tab-line{
					border-bottom: 6upx solid #FEDE33;
					width: 70upx;
					margin: auto;
					border-top: 6upx solid #FEDE33;
					border-radius:20upx;
				}
			}
		}
	}
</style>
