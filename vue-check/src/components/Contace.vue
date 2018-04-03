<template>
	<div class="contace clearfix">
		<div class="contace_text">
			<div class="block_kuai"></div>
			<p>联系我们 - CONTACE</p>
		</div>
		<ul>
			<li v-for="i in arr">
				<p>{{i.name}} <img src="../assets/img/8.png" alt="" /></p>
				<p class="p2">{{i.num}}</p>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				arr:[]
			}
		},
		created(){
			this.$http.get("http://localhost:3000/contace").then(e=>this.arr=e.body)
		}
	}
</script>

<style>
	.contace{
		margin-right: 8%;
		width: 20%;
		height: 265px;
		background-color: #F7F7F7;
		float: right;
		font-size: 14px;
		margin-top: 10px;
	}
	.contace_text{
		height: 70px;
		line-height: 70px;
	}
	.block_kuai{
		width: 20px;
		height: 20px;
		background-color: #000000;
		float: left;
		margin: 25px 15px;
	}
	
	.contace li{
		list-style: none;
		line-height: 23px;
		margin-left: 15px;
		margin-bottom: 20px;
	}
	.contace li .p2{
		color: blue;
	}
</style>