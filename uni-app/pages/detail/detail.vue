<template>
<!-- 	<view>
		<view>
			<text>唱跳rap</text>
		</view>
		<view>
			<text user-select="true">唱跳rap</text>
		</view>
		<view>
			<text selectable="true">唱跳rap</text>
		</view>
		<view>
			<text selectable="true" space="ensp">唱跳 rap</text>
		</view>
	</view> -->
	<view>
		<view class="box2" hover-class="box2-active">
			<view class="box" hover-start-time="1000" hover-stay-time="1000" hover-class="box-active" hover-stop-propagation="true">我是一个盒子</view>
		</view>
		<button size="default">按钮</button>
		<button size="mini">按钮</button>
		<button type="primary" plain loading>按钮</button>
	</view>

</template>

<script>
</script>

<style>
	.box2 {
		width: 150px;
		height: 200px;
		background-color: aquamarine;
	}
	.box2-active {
		background-color: blanchedalmond;
	}
	.box {
		width: 100px;
		height: 100px;
		background-color: green;
	}
	.box-active {
		background-color: red;
	}
</style>