<template>
	<div class="newloupan clearfix">
		<div class="newloupan_text">
			<div class="newloupan_text_title">
				<p class="p1">全新楼盘</p> 
				<p class="p2">- New Apartment -</p>
			</div>
			<div class="lou" v-for="i in arr">
				<img :src="i.img">
				<ul>
					<li class="name">{{i.name}}</li>
					<li>地区：{{i.des}}</li>
					<li>户型：{{i.house}}</li>
					<li>价格：{{i.price}}</li>
				</ul>
			</div>
			<div class="more">
				<button>浏览更多楼盘</button>
			</div>
		</div>
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
			this.$http.get("http://localhost:3000").then(e=>this.arr=e.body)
		}
	}
</script>

<style>
	.newloupan{
		width: 61%;
		height: 505px;
		background-color: #F7F7F7;
		float: left;
		margin-left: 9%;
		border: 1px solid #ccc;
		margin-bottom: 40px;
	}
	.newloupan_text_title{
		height: 100px;
		text-align: center;
	}
	.newloupan_text_title .p1{
		font-size: 20px;
		line-height: 30px;
		padding-top: 30px;
	}
	.newloupan_text_title .p2{
		font-size: 14px;
		color: #ccc;
	}
	.lou{
		width: 33%;
		height: 320px;
		background-color: #ffffff;
		float: left;
		margin-left: 0.3%;
	}
	.lou img{
		width: 100%;
		height: 175px;
	}
	.newloupan li{
		font-size: 13px;
		line-height: 22px;
		list-style: none;
		margin-left: 15px;
	}
	.lou .name{
		line-height: 55px;
		font-size: 16px;
	}
	.more{
		width: 100%;
		height: 85px;
		float: left;
	}
	.more button{
		width: 135px;
		height: 38px;
		font-size: 12px;
		background-color: #F7F7F7;
		margin-top: 23px;
		margin-left: 40%;
	}
</style>