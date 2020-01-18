<template>

	
	<div class="round">
			<div class="roundtitle">
				<!-- 圆桌上面的导航栏 -->
			<ul class="roundnavbar">
				<li class="leftround"><span style="color: #8590A6;font-size: 15px;float: left;margin-left: 20px;">圆桌</span></li>
				<li class="rightround"><span style="color: #1E90FF;font-size: 15px;float: left;margin-left: 820px;">举办圆桌</span></li>		
		</ul>
		</div>
		
		<div class="round_info">
			<div class="info" v-for="(item, index) in roundtableall" :key="index">
				<div class="roundabout">
					<div ><img :src="item.banner" class="round_img" /></div>
					</div>
					<div>
						<h3 class="round_name">{{ item.name }}</h3>		
					</div>	
				
				<span class="round_visitsCount">该圆桌被浏览&nbsp;{{ item.visitsCount }} 次</span>
										
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			roundtableall: []
		};
	},
	created() {
		this.getData();
	},
	methods: {
		getData() {
			this.axios.get('http://localhost:8080/api/roundtable/all').then(res => {
				this.roundtableall = res.data.data;
			});
		}
	}
};
</script>

<style>
	.round{
		height: 1000px;
		width: 1000px;
		background: #FFFFFF;
		margin: 0 auto;
		}

.round_info {
	float: left;
	display: inline-block;
	width: auto;
	margin-top: 10px;
	
	
}
.info {
	
	margin: 20px;
	float: left;
	background-color: white;
	position: relative;
	width: 200px;
	height: 200px;
	border-radius: 5px;
	border: 1px solid gainsboro;
	border-radius: 10px;
	margin-top: 10px;
	
	
}
.round_img {
	width: 200px;
	height: 200px;
	border-radius: 10px;
	
	
}
.round_name {
	position: absolute;
	top: 170px;
	left: 5px;
	right: 5px;
	font-size: 14px;
	font-weight: 500;
	color: white;
	font-weight: 500;
}
span {
	display: block;
	margin-left: 10px;
	margin-top: 5px;
	color: gray;
	font-size: 14px;
}
.roundtitle{
	margin-top: 10px;
}



</style>