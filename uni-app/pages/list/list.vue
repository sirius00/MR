<template>
	<view>
		<view>
			<button type="primary" @click="setStorage">存储数据</button>
			<button type="primary" @click="upLoadP">上传图片</button>
			<image v-for="item in imgArr" :src="item"  @click="preView(item)"></image>
			
			<!-- #ifdef H5 -->
			<view>h5中可见</view>
			<!-- #endif -->
			
			<!-- #ifdef MP-WEIXIN -->
			<view>小程序中可见</view>
			<!-- #endif -->
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr: []
			}
		},
		methods: {
			setStorage() {
				uni.setStorage({
					key: "id",
					data: "test storage",
					success() {
						console.log('success')
					}
				})
			},
			upLoadP() {
				uni.chooseImage({
					count: 6,
					success: res => {
						console.log('上传成功')
						this.imgArr = res.tempFilePaths
					}
				})
			},
			preView(current) {
				// console.log(current)
				uni.previewImage({
					current,
					urls: this.imgArr,
					indicator: Number
				})
			},
			onLoad() {
				// #ifdef H5
					console.log("h5中打印")
				// #endif
				
				console.log("微信小程序中打印")
			}
		}
	}
</script>

<style>

</style>
