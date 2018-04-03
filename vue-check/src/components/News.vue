<template>
	<div class="news clearfix">
		<div class="news_text">
			<div class="block_kuai"></div>
			<p>楼市动向 - NEWS&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>阅读更多</span></p>
		</div>
		<ul>
			<li v-for="i in arr">
				<p>{{i.p1}}</p>
				<p class="p2">{{i.p2}}</p>
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
			this.$http.get("http://localhost:3000/news").then(e=>this.arr=e.body)
		}
	}
</script>

<style>
	.news{
		margin-right: 8%;
		width: 20%;
		height: 485px;
		background-color: #F7F7F7;
		float: right;
		font-size: 14px;
	}
	.news_text{
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
	
	.news_text span{
		font-weight: 200;
		font-size: 12px;
		padding: 5px;
		border: 1px solid #000000;
	}
	
	.news li{
		list-style: none;
		line-height: 23px;
		margin-left: 15px;
		margin-bottom: 24px;
	}
	.news li .p2{
		color: #ccc;
	}
</style>