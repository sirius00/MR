<template>
	<view>
		<view v-for="item in arr" :key="item.id">
			名字:{{item.name}},年龄:{{item.age}}
		</view>
		<button type="primary" @click="clickHandle">按钮</button>
		<br>
		<button type="primary" @click="checkTest">切换test组件</button>
		<test v-if="flag" :title="title" @myEven="getNum"></test>
	</view>
</template>

<script>
	import test from "../../components/test/test.vue"
	export default {
		data() {
			return {
				arr: [{
						name: "宋小宝",
						age: 20,
						id: 1
					},
					{
						name: "赵四",
						age: 20,
						id: 2
					},
					{
						name: "刘能",
						age: 20,
						id: 3
					}
				],
				flag: true,
				title: '组件通讯-父传子'
			}
		},

		methods: {
			clickHandle() {
				console.log("click")
			},
			checkTest() {
				this.flag = !this.flag
			},
			getNum(num) {
				console.log(num);	
			}
		},
	}
</script>

<style>
</style>
