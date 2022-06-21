<template>
	<view>
		<button @click="addNum">修改b组件的数据</button>
	</view>
</template>

<script>
	export default {
		name:"a",
		data() {
			return {
				num: 10
			};
		},
		methods: {
			addNum() {
				uni.$emit('update',this.num)
			}
		}
	}
</script>

<style>

</style>