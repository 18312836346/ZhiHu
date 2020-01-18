<template>
	<div>
		<div class="container">
			<div class="head">
				<img class="pic-all1" src="../assets/image/all.png"/>
			
				<h2 style="margin-top: 20px; margin-bottom: 20px; font-size: 30px;">最新专题</h2>
			</div>
			<!-- 显示内容 -->
			<div class="row">
				<div class="card1" v-for="(item, index) in specials" :key="index">
					<!-- 图片 -->
					<img :src="item.banner" alt="" />
					<div class="w-row" >
						<div class="left">
						<!-- 标题 -->
						<h3>{{ item.title }}</h3>
						<!-- 小字 -->
						<span style="color: #8590A6;font-size: 12px;" class="meta">{{ item.updated }}更新·{{ item.viewCount }}浏览</span></div>
						<div class="right">
							<!-- 关注按钮 -->
							<button class="button"><h3>关注专题</h3></button>
                            <span v-for="(section,index) in item.sections" :key="index" class="section1">
							{{section.sectionTitle}}
							
							</span>
						</div>
							
					</div>
                      <p class="introduction">{{ item.introduction }}</p>
					 <span v-for="(section, index) in item.sections" :key="index" class="section">{{section.sectionTitle}}</span>
					
				</div>
			</div>
			
			<div class="topic">
				<router-link to="/special/all" class="btn"><button class="button-topic"><h3 style="color: #A9A9A9;">查看更多专题 ></h3></button></router-link>
			</div>
			
		</div>
		
		
		<!-- 圆桌讨论 -->
		<div class="container1">
			<div class="head">
				<!-- 图标 -->
				<img class="pic-all1" src="../assets/image/all.png"/>
				<h2 style="margin-top: 20px; margin-bottom: 20px; font-size: 30px;">圆桌讨论</h2>
			</div>
			<!-- 显示内容 -->
			<div class="row">
				<div class="card2" v-for="(item, index) in roundtable" :key="index">
					<!-- 图片 -->
						<img :src="item.banner" alt=""  />
					<div class="little-card">
					<router-link :to="{ path: '/roundtable/' + item.urlToken }">
						<div class="left">
							<h3 class="nameround">{{ item.name }}</h3>
							<span style="color: #8590A6;font-size: 12px;" class="meta">{{ item.includeCount }}位嘉宾参与 |  {{ item.visitsCount }}人关注</span>
						</div>
					</router-link>
					</div>
					<div class="roundbutton">
					<button class="button"><h3>关注圆桌</h3></button>
					</div>
				</div>
			</div>
			</div>

		<div class="topic">
			<router-link to="/roundtable" class="btn"><button class="button-topic"><h3 style="color: #A9A9A9;">查看更多圆桌 ></h3></button></router-link>
		</div>
		
	</div>
</template>

<script>
export default {
	name: 'hot',
	data() {
		return {
			specials: [],
			roundtable: []
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/roundtable').then(res => {
					console.log(res);
					this.roundtable = res.data.data;
				});
	
		this.axios.get('http://localhost:8080/api/special').then(res => {
			console.log(res);
			this.specials = res.data.data;
		});
	   
	}
};
</script>

<style lang="scss" scoped>
@font-face {
	font-family: 'iconfont'; 
	src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot');
	src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot?#iefix') format('embedded-opentype'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff2') format('woff2'),
		url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff') format('woff'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.ttf') format('truetype'),
		url('//at.alicdn.com/t/font_1616266_b8gknsgz736.svg#iconfont') format('svg');
}
.iconfont {
	font-family: 'iconfont' !important;
	font-size: 30px;
	font-style: normal;
	-webkit-font-smoothing: antialiased;
	-webkit-text-stroke-width: 0.2px;
	-moz-osx-font-smoothing: grayscale;
	color: blue;
	margin: 10px;	
}
.row {
	margin: 0 auto;
	display: flex;
	flex-wrap: wrap;
}
.container {
	display: block;
	margin: auto;
	width: 70%;
	margin-top: 15px;
}
.head {
	display: flex;
	align-items: center;
}
.card1 {
	box-shadow: 2px 5px 5px #aaa;
	width: 46%;
	margin: 1%;
	height: 430px;
	background-color: rgb(255,255,255);
}
.card1 img {
	border-radius: 5px;
	width: 100%;
	
}
.left{
	height: 100px;
	width: 80%;
	padding: 25px;
	
}
.left h5{
	color: darkgray;
}
.right{
	height: 100px;
	width: 20%;
	padding-top: 30px;
}
.button{
	width: 90%;
	border: none;
	background-color: rgb(235,245,255);
	color: rgb(30,134,255);
	height: 40px;
	border-radius: 5px;
	}
.introduction{
margin: 20px;
text-indent:50px;
}
.topic{
	margin-top: 20px;
	height: 100px;
	text-align: center;
	margin-left: -35px;
}
.button-topic{
	border: none;
	width: 160px;
	background-color: rgb(255,255,255);
	height: 50px;
	border-radius: 50px;
}
.section1{
			background-color: rgb(246,246,246);
			width: auto;
			margin-right: 10px;
			padding: 2px;
			font-size: 13px;
			border-radius: 5px;
		}
.card2 {
	box-shadow: 2px 5px 5px #aaa;
	width: 46%;
	margin: 1%;
	height: 430px;
	background-color: rgb(255, 255, 255);
}
.card2 img {
	border-radius: 5px;
	width: 100%;
	height: 60%;
	background: rgba(0,0,0,0.3);
	z-index: 999;
}
.container1 {
	display: block;
	margin: auto;
	width: 70%;
	margin-top: -70px;
}


</style>