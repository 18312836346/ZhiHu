<template>
	<div class="all" style="margin: 0 auto;">
		<div class="container" style="margin-left: 300px;">
			<div class="head">
				<img class="pic-all1" src="../assets/image/special.png" />

				<h2 style="margin-top: 20px; margin-bottom: 20px; font-size: 30px;">最新专题</h2>
			</div>
			<!-- 显示内容 -->
			<div class="row">
				<div class="card1" v-for="(item, index) in specials" :key="index">
					<!--图片 -->
					<img :src="item.banner" alt="" />
					<div class="w-row">
						<div class="left">
							<!-- 标题 -->
							<h3>{{ item.title }}</h3>
							<!-- 小字 -->
							<span style="color: #8590A6;font-size: 12px;" class="meta">{{ item.updated }}更新·{{ item.viewCount }}浏览</span>
						</div>
						<div class="right">
							<!-- 关注按钮 -->
							<button class="button">
								<h3>关注专题</h3>
							</button>

						</div>

					</div>
					<div>
						<!-- 水平线 -->
						<hr style="border: 1px solid #E5E5E5;color: #E5E5E5; width: 90%; margin: 0 auto;">
						<!-- 因没有标签和概括内容这里是描述 -->
						<p class="introduction">{{ item.introduction }}</p>

					</div>

				</div>
			</div>
			<!-- 查看更多：使其跳转到全部专题页面 -->
			<div class="topic" style="margin-left: -70px;">
				<router-link to="/special/all" class="btn"><button class="button-topic">
						<h3 style="color: #A9A9A9;">查看更多专题 ></h3>
					</button></router-link>
			</div>

		</div>


		<!-- 圆桌讨论 -->
		<div class="container1" style="margin-left: 300px;">
			<div class="head">
				<!-- 图标 -->
				<img class="pic-roundtable" src="../assets/image/roundtable.png" />
				<h2 style="margin-top: 20px; margin-bottom: 20px;margin-left: 10px; font-size: 30px;">圆桌讨论</h2>
			</div>

			<div class="row">
				<div class="roundtable" v-for="(item, index) in roundtable" :key="index">
					<div class="w-row">
						<div class="shadow">
						</div>
						<img :src="item.banner" alt="" />
					</div>
					<div class="w-row">
						<div class="round-left">
							<h3>{{item.name }}</h3>

							<h5 class="concern">{{item.includeCount}}位嘉宾参与 | {{item.visitsCount}}人关注</h5>
						</div>
						<div class="round-right">
							<button class="button">
								<h4>关注圆桌</h4>
							</button>
						</div>
					</div>
					<p class="v" style="margin: 30px;">{{item.urlToken }}</p>
				</div>
			</div>
		</div>
		<div class="topic" style="margin-left: 50px;">
			<router-link to="/roundtable" class="btn"><button class="button-topic">
					<h3 style="color: #A9A9A9;">查看更多圆桌 ></h3>
				</button></router-link>
		</div>

		<!-- 热门收藏夹 -->
		<div class="container2" style="margin-left: 300px;">
			<div class="head">
				<!-- 图标 -->
				<img class="pic-favorite" src="../assets/image/favorite.png" />
				<h2 style="margin-top: 20px; margin-bottom: 20px;margin-left: 10px; font-size: 30px;">热门收藏夹</h2>
			</div>
			<div class="row">
				<div class="favorite" v-for="(item, index) in favorite" :key="index">
					<div class="fav-top">
						<!-- 标题 -->
						<div class="fav-title" style="padding: 30px;">
							<h3>{{item.title }}</h3>
						</div>
						<!-- 关注按钮 -->
						<div style="padding: 30px;margin-left: 320px; margin-top: -80px;">
							<button class="fav-button">
								<h4>关注收藏夹</h4>
							</button>
						</div>
						<!-- 用户头像 -->
						<div class="author-header" style="padding: 30px;margin-top: -40px;">
							<img :src="item.creatorAvatar" alt="" style="float: left;" />
							<!-- 用户名 -->
							<span style="float: left;color: #000000;">{{item.creatorName}}</span><span style="float: left;color: #8590A6;font-size: 15px;">&nbsp;&nbsp;创建&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;{{item.followers}}人关注</span>
						</div>
					</div>

					<!-- 水平线 -->
					<div>
						<hr style="border: 1px solid #E5E5E5;color: #E5E5E5; width: 90%; margin: 0 auto; margin-top: 25px;">
					</div>

					<div class="fav-bottom">
						<!-- 问题标题 -->
						<div class="fav-question" style="margin-top: -5px;">
							<h4>
								<p style="padding: 30px;">{{item.questionTitle}}</p>
							</h4>
						</div>
						<!-- 回答内容 -->
						<div class="fav-content">
							<!-- nobr标签不会换行 -->
							<nobr><span class="content">{{item.answerContent}}</span></nobr>
						</div>
						<!-- 赞与评论 -->
						<div class="fav-voteup" style="padding: 30px; margin-top: -30px;font-size: 8px;margin-left: -5px;">
							<span>{{item.voteupCount}}&nbsp;赞同&nbsp;·&nbsp;{{item.commentCount}}&nbsp;评论&nbsp;</span>
						</div>
						<div class="fav-favorite-count" style="margin-top: -10px;padding: 30px;margin-left: -5px;margin-top: -30px;">
							<h2><span style="color: #8590A6;font-size: 15px;">已收藏{{item.totalCount}}条内容&nbsp;&nbsp;></span></h2>
						</div>
					</div>

				</div>
				<div class="topic" style="margin-left: -60px;">
					<router-link to="/favorite" class="btn">
						<button class="button-topic" style="margin-left: 470px;">
							<h3 style="color: #A9A9A9; ;">查看更多收藏夹&nbsp;></h3>
						</button></router-link>
				</div>
			</div>
		</div>

		<!-- 专栏 -->
		<div class="columns" style="margin-left: 300px;">
			<div class="head">
				<!-- 从知乎拷来的svg图标 -->
				<svg class="columns-img" fill="currentColor" viewBox="0 0 24 24" width="36" height="36">
					<path d="M12 22C6.477 22 2 17.523 2 12S6.477 2 12 2s10 4.477 10 10-4.477 10-10 10zm4.043-15.524a.745.745 
	0 0 0-1.053.017l-6.857 7.071 2.237 2.17 6.857-7.071a.743.743 0 0 0-.016-1.052l-1.168-1.135zm-9.028 9.476l-.348 
	1.381 1.37-.39 1.274-.36-1.973-1.916-.323 1.285z"
					 fill-rule="evenodd"></path>
				</svg>
				<h2 style="margin-top: 20px; margin-bottom: 20px;margin-left: 10px; font-size: 30px;">专栏</h2>
			</div>
		</div>
		<div class="row2">
			<div class="row-columns" v-for="(item, index) in columns" :key="index">
				<!-- 头像 -->
			
				<div class="columns-header" style="width: 70px; height: 70px;border-radius: 50%; overflow: hidden;margin:  0 auto; margin-top: 20px;">
					<img :src="item.imageUrl" alt="" style="width: 100%;"/>
				</div>
				
				<!-- title -->
	
				<div class="columnbs-title">
					<onbr><h2><span style="color: #000000;">{{item.title}}</span></h2></onbr>
				</div>
				<!-- 关注与文章 -->
				<div class="cloumnbs-followers-articles_count">
					<span style="font-size: 12px; text-align: center;">{{item.followers}}&nbsp;关注&nbsp;·&nbsp;{{item.articlesCount}}&nbsp;文章</span>
				</div>
				<!-- 介绍 -->
				<div class="columnbs-description" style="height:auto; text-overflow: ellipsis; overflow: hidden;margin-top: 15px;text-align: center;">
				<onbr><span style="font-size: 13px;text-align: center;color: #000000;">{{item.description}}</span></onbr>
				</div>
				<!-- 进入专栏按钮 -->
				<a v-bind:href="item.url" style="text-decoration: none;display:block;">
					<div class="columnbs-button" style="height: 35px;width:100px;margin: 0 auto; margin-top: 20px;">
						<!-- 关注按钮 -->
				
					<button class="button" style="height: 35px;width:100px;margin: 0 auto;border: 1px solid; border-color: #4CAF50;background-color: #FFFFFF;">
							<h4 style="color: #4CAF50;">进入专栏</h4>
					</button>
					</div></a>
			</div>
				<div class="topic" style="margin-left: -60px;">
				<router-link to="/columns" class="btn">
					<button class="button-topic" style="margin-left: 470px;">
						<h3 style="color: #A9A9A9; ;">查看更多专栏&nbsp;></h3>
					</button></router-link>
			</div>
		</div>
		
	</div>


</template>

<script>
	export default {
		name: 'hot',
		data() {
			return {
				specials: [],
				roundtable: [],
				favorite: [],
				columns:[],
			};
		},
		created() {
			// 专栏的接口获取
			this.axios.get('http://localhost:8080/api/columns').then(res => {
				console.log(res);
				this.columns = res.data.data;
			});
			// 圆桌讨论的接口获取
			this.axios.get('http://localhost:8080/api/favorite').then(res => {
				console.log(res);
				this.favorite = res.data.data;
			});
			// 圆桌讨论的接口获取
			this.axios.get('http://localhost:8080/api/roundtable').then(res => {
				console.log(res);
				this.roundtable = res.data.data;
			});
			// 最新专题的接口获取
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
		border-radius: 10px;
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
		width: 44%;
		margin: 1%;
		height: 440px;
		background-color: rgb(255, 255, 255);
	}

	.card1 img {
		border-radius: 5px;
		width: 100%;
		height: 200px;

	}

	.left {
		height: 100px;
		width: 80%;
		padding: 25px;

	}

	.left h5 {
		color: darkgray;
	}

	.right {
		height: 100px;
		width: 20%;
		padding-top: 30px;
	}

	.button {
		width: 90%;
		border: none;
		background-color: rgb(235, 245, 255);
		color: rgb(30, 134, 255);
		height: 40px;
		border-radius: 5px;
	}

	.introduction {
		margin: 20px;
		text-indent: 50px;
	}

	.topic {
		margin-top: 20px;
		height: 100px;
		text-align: center;
		margin-left: -35px;
	}

	.button-topic {
		border: none;
		width: 160px;
		background-color: rgb(255, 255, 255);
		height: 50px;
		border-radius: 50px;
	}

	.section {
		float: left;
		background-color: rgb(246, 246, 246);
		width: auto;
		margin-right: 10px;
		padding: 2px;
		font-size: 13px;
		border-radius: 5px;
		height: auto;
	}

	.section1 {
		background-color: rgb(246, 246, 246);
		width: auto;
		margin-right: 10px;
		padding: 2px;
		font-size: 13px;
		border-radius: 5px;
	}

	.container1 {
		display: block;
		margin: 0 auto;
		width: 70%;
		margin-top: 15px;
	}

	// 圆桌卡片样式
	.roundtable {
		box-shadow: 2px 5px 5px #aaa;
		width: 44%;
		margin: 1%;
		height: 360px;
		background-color: rgb(255, 255, 255);
		position: relative;
	}

	.roundtable img {
		border-radius: 5px;
		width: 50%;
		height: 50%;
		position: absolute;
		right: 0;


	}

	.shadow {
		z-index: 10;
		width: 100%;
		height: 220px;
		text-align: center;
		background-image: linear-gradient(to right, #e66465, #9198e5, rgba(255, 255, 255, 0));


	}

	.round-left {
		position: absolute;
		top: 70px;
		left: 25px;
		width: 70%;
		color: white;
		z-index: 11;
	}

	.a {
		margin-top: 15px;
		height: 65px;
		width: 100%;
	}

	.concern {
		margin-left: 80px;
		margin-top: 80px;
	}

	.round-right {
		position: absolute;
		top: 160px;
		right: 0;
		width: 23%;
	}


	.container2 {
		display: block;
		margin: auto;
		width: 70%;
		margin-top: 15px;
	}

	// 热门收藏夹的框
	.favorite {
		box-shadow: 2px 5px 5px #aaa;
		width: 44%;
		margin: 1%;
		height: 320px;
		background-color: rgb(255, 255, 255);
	}

	.fav-button {
		width: 100px;
		border: none;
		background-color: rgb(235, 245, 255);
		color: rgb(30, 134, 255);
		height: 30px;
		font-size: 15px;
		border-radius: 5px;
	}

	.content {
		height: 20px;
		text-overflow: ellipsis;
		overflow: hidden;
		margin-top: -20px;
		margin-left: 30px;
		color: #000000;
		font-size: 15px;
	}

// 专栏
	.columns {
		display: block;
		margin: auto;
		width: 70%;
		margin-top: 15px;
	}

	.columns-img {
		fill: #0084ff;
		height: 40px;
		width: 40px;
		margin-top: 1px;
		margin-left: 15px;
	}
	.row-columns{
	
		box-shadow: 1px 3px 3px #aaa;
		width: 210px;
		margin: 15px;
		height: 280px;
		background-color: rgb(255, 255, 255);
	}
	
	.row2 {
		
		margin-left: 300px;
		display: flex;
		flex-wrap: wrap;
		border-radius: 10px;
		width: 1000px;
		height: auto;
	}
	.columnbs-title{
		height:auto;
		text-overflow: ellipsis;
		overflow: hidden;
		color: #000000;
		font-size: 15px;
		text-align: center;
		margin-left: -5px;
		margin-top: 15px;
	}
	.columnbs-description{
		
		text-overflow: ellipsis;
		overflow: hidden;
		color: #000000;
		font-size: 15px;
	}

</style>
