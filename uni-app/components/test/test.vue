<template>
	<view>
		这是测试组件test
		父组件传递过来的数据----{{title}}
		<button @click="sendNum">给父组件传值</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num: 3,
				initId: null,
			}
		},
		props:['title'],
		beforeCreated() {
			console.log("实例已经开始初始化了")
			console.log(this.num)
		},
		created() {
			console.log('created', this.num)
			this.initId = setInterval(() => {
				console.log("执行定时器")
			}, 1000)
		},
		destroyed() {
			console.log("组件销毁了")
			clearInterval(this.initId)
		},
		methods: {
			sendNum() {
				console.log("给父组件传值");
					this.$emit('myEven', this.num)
			}
		}
	}
</script>

<style>
</style>
