<template>
	<view class="content">
		<!-- <test :msg="msg" @testShowName="testEvent"></test> -->
		<text>index</text>
		{{"msg"}}
		<view>{{msg}}</view>
		<view>{{msg+"mesa"}}</view>
		<view>{{"msea".indexOf("sea")!==-1?"1":"2"}}</view>
		<view>{{"wdnmd".slice(0,1)}}</view>
		<image :src="javascript"></image>
		<view 
		  v-for="(item,index) in names" 
		  :key="index"
		  class="{box3:index==currentindex}"
		  @click="setIndexNumber(index)"
		>
		  {{item}}
		</view>
		
	</view>
</template>

<script>
	import test from "../../components/test.vue";
	export default {
		data() {
			return {
				msg: "lili",
				url: "../../static/one.png",
				names:['1','2','3','4'],
				currentindex:0,
			}
		},
		components:{
			test
		},
		onLoad() {
			uni.$on("testEmit",(res)=>{
				console.log(res);
			})

		},
		methods: {
			setIndexNumber(index){
				this.currentindex = index;
			}

		}
	}
</script>

<style>
	
.box1{
	background: #007AFF;
}
.box2{
	background: #2C405A;
}
.box3{
	background: #2a2a2a;
	height: 100px;
	width:350;
	border: 9px solid #000000;
	margin-left:5px;
	margin-right: 5px;
}
</style>
