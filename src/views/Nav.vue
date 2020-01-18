<template>
	
	<!-- 大的导航栏 首页 发现 等你来答 TODO:还需要添加许多 -->
	<div>
		<ul class="container" style="background: #FFFFFF;">
		<img src="../assets/image/zhihu.png" style="margin-left: 320px; height: 40px;" />
		<li class="b"><router-link to="/home"><span style="color: #8590A6;font-size: 15px;">首页</span></router-link></li>
		<li class="b"><router-link to="/explore"><span style="color: #8590A6;font-size: 15px;">发现</span></router-link></li>
		<li class="b"><router-link to="/question/waiting"><span style="color: #8590A6;font-size: 15px;">等你来答</span></router-link></li>
		<li class="login" ><router-link to="/login" style="color: #000000;">登录</router-link></li>
		</ul>
		<!-- 路由 -->
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
	
	 //大导航栏的样式 
	.container{
		background-color:white;
		height: 50px;
		width: 100%;
		display: flex;
		align-items: center;
		box-shadow: 2px 5px 5px #aaa;
		align-items: center;
		
		
	}
	// 知乎样式
	.container img{
		height: 100%;
		width: auto;
		margin-right: 30px;
		margin-left: 500px;
	}
	.b {
		width: 5%;
	}
	h4{
		color: lightgray;
	}
</style>