<template>
	<div>
		<ul class="container" style="background: #FFFFFF;">
		<img src="../assets/image/zhihu.png" style="margin-left: 160px; height: 40px;" />
		<li class="b"><router-link to="/home"><span style="color: #8590A6;font-size: 15px;">首页</span></router-link></li>
		<li class="b"><router-link to="/explore"><span style="color: #8590A6;font-size: 15px;">发现</span></router-link></li>
		<li class="b"><router-link to="/question/waiting"><span style="color: #8590A6;font-size: 15px;">等你来答</span></router-link></li>
		 <a class="login" href="https://www.zhihu.com/signin?next=%2F">登录</a>
		
		</ul>
	<router-view />
	</div>
</template>

<script>
	export default{
		name:'Navbar',
		data() {
			return{};
		},
		created() {}
	};
</script>

<style lang="scss" scoped>
	.container{
		background-color:white;
		height: 50px;
		width: 100%;
		display: flex;
		align-items: center;
		box-shadow: 2px 5px 5px #aaa;
		align-items: center;
		
		
	}
	.container img{
		height: 100%;
		width: auto;
		margin-right: 50px;
		margin-left: 110px;
	}
	.b {
		width: 4%;
	}
	h4{
		color: lightgray;
	}
</style>