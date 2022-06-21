<template>
	<view>
		这是b组件的数据:{{num}}
	</view>
</template>

<script>
	export default {
		name:"b",
		data() {
			return {
				num: 0
			};
		},
		created() {
			uni.$on('update', num => {
				this.num += num
			})
		}
	}
</script>

<style>

</style>