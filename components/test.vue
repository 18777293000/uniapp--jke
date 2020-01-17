<template>
	<view>
		<button type="primary" @click="test" class="btn">updata</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props:["msg"],
		methods:{
			test(){
				//this.$emit("testShowName",{name:"Msea"})
				uni.$emit("testEmit",{name:"luce"})
			}
		}
	}
</script>

<style>
.btn{
	position: fixed;
	top:450px;
	right:20px;
	background: #ffff07;
	color: #333333;
}
</style>
