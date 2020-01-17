<template>
	<div>
		<div class="container">
			
			<div class="container-home">
				<div class="container-left">
					<!-- 推荐关注热榜导航栏 -->
				<ul class="navbar">
					<li class="three"><router-link to="/home"><span style="color: #8590A6;font-size: 15px;">推荐</span></router-link></li>
					<li class="three"><router-link to="/home/follow"><span style="color: #8590A6;font-size: 15px;">关注</span></router-link></li>
					<li class="three"><router-link to="/home/hot"><span style="color: #8590A6;font-size: 15px;">热榜</span></router-link></li>
			</ul>
			<router-view />
			</div>
			
			<div class="container-right">
				<div class="home-right-top"></div>
				<div  class="home-right-mid"></div>
				<div  class="home-right-mid2"></div>
				<div  class="home-right-bottom"></div>
				
			</div>
		
			
			
			</div>
			</div>
		</div>
</template>

<script>
	export default{
		name:'special',
		data(){
			return{
				specials:[]
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/special/all').then(res =>{
				console.log(res);
				this.specials = res.data.data;
			});
		}
	};
</script>

<style lang="scss" scoped>
	.container{
		height: 1000px;
		background-color: rgb(246,246,246);
		margin-top: 10px;
	}
	.container-home{
		
		display: block;
		    margin: auto;
		    width: 80%;
						height: 1000px;
				
			border-radius: 5px;
			display: flex;
	}
	.container-left{
		background-color: rgb(255,255,255);
		width: 68%;
	}
	.navbar{
		height: 60px;
		border-bottom: 1px solid rgb(246,246,246);
		display: flex;
		align-items: center;
		
		
	}
	.three{
		width: 8%;
		margin-left: 15px;
	}
	.three h4{
		color: black;
	}
	.container-right{
		width: 30%;
		
		height: 500px;
		margin-left: 5px;
	}
	.home-right-top{
		height: 230px;
		width: 90%;
		background-color: white;
		margin: 3%;	
		border: 1px solid #e0e0e0;
	}
	.home-right-mid{
		margin-top: 10px;
		height: 230px;
		width: 90%;
		margin: 3%;
		background-color: white;
		border: 1px solid #e0e0e0;
	}
		.home-right-mid2{
		margin-top: 10px;
		height: 230px;
		width: 90%;
		margin: 3%;
		background-color: white;
		border: 1px solid #e0e0e0;
	}
	.home-right-bottom{
				margin-top: 10px;
		
		height: 230px;
		width: 90%;
		background-color: white;
		margin: 3%;
		border: 1px solid #e0e0e0;
	}
</style>