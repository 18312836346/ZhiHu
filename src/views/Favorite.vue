<template>
	<div>
		<div class="hot-fav" style="width: 100%; height: 80px;background-color: #FFFFFF; margin-top: 10px;">
			<img src="../assets/image/favorite.png" alt="" class="pic-favorite" style="float: left;margin-left: 300px; margin-top: 20px;align-content: center;">
			<h2 style="float: left; margin-left: 10px; margin-top: 20px;">热门收藏夹</h2>
		</div>

		<div class="container">
			<div class="fav" v-for="(item,index) in favorite" :key="index">
				<div class="left" style="width:35%;">
					<!-- 标题 -->
					<h2><span style="color: #000000;margin-top: 10px; width: 100px;">{{item.title}}</span></h2>
					<!-- 头像、名字 -->
					<div class="hot-fav-head" style="padding: 10px;">
						<img :src="item.creatorAvatar" alt="" style="float: left; margin-top: 5px;" />
						<span style="float: left;color: #000000;margin-top: 12px;">{{item.creatorName}}</span>
						<span style="float: left;color: #8590A6;font-size: 12px;margin-top: 14px;">&nbsp;&nbsp;创建&nbsp;&nbsp;</span>
				
					</div>
		       	  <div style="padding: 10px;margin-top: 40px;">
		       	<button class="hot-fav-button">
		       		<h5>关注收藏夹</h5>
		       	</button>
				<div  style="float: left;font-size: 12px;">
				<span>{{item.followers}}人关注</span>
				</div>
		       </div>
				</div>
				
				<div style="height: 118px; width: 1px;margin-top: 10px; background-color:#EEEEEE"></div>
				<div style="padding: 10px;margin-left: 10px; width: 77%;">
					<div>
						<h2><span style="color: #000000;">{{item.questionTitle}}</span></h2>
					</div>
				      <div class="hot-fav-content">
						  <span style="color: #000000;">{{item.answerContent}}</span>
					  </div>
					  <div>
						  <span>{{item.voteupCount}}&nbsp;赞同&nbsp;·&nbsp;{{item.commentCount}}&nbsp;评论&nbsp;</span>
					  </div>
					  <div class="fav-favorite-count" style="padding: 10px;margin-left: -10px;">
					  	<span style="color: #8590A6;font-size: 15px;">已收藏{{item.totalCount}}条内容&nbsp;&nbsp;&nbsp;></span>
					  </div>
				</div>
			</div>


		</div>

	</div>
</template>

<script>
	export default {
		name: 'hot',
		data() {
			return {
				favorite: []
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/favorite/all').then(res => {
				console.log(res);
				this.favorite = res.data.data;
			});
		}
	};
</script>

<style lang="scss" scoped>
	@font-face {
		font-family: 'iconfont';
		/* project id 1616266 */
		src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot');
		src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot?#iefix') format('embedded-opentype'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff2') format('woff2'),
			url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff') format('woff'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.ttf') format('truetype'),
			url('//at.alicdn.com/t/font_1616266_b8gknsgz736.svg#iconfont') format('svg');
	}


	.fav {
		background-color: rgb(255, 255, 255);
		display: flex;
		height: 160px;
		margin: 15px;
		width: 60%;
		margin: 0 auto;
		margin-top: 10px;
		padding: 10px;

	}
	.hot-fav-button{
			width: 100px;
		border: none;
		background-color: rgb(235, 245, 255);
		color: rgb(30, 134, 255);
		height: 30px;
		font-size: 15px;
		border-radius: 5px;
		float:left;
	}
		.hot-fav-content {
		overflow: hidden;
		text-overflow: ellipsis; //显示省略号
		display: -webkit-box;
		-webkit-line-clamp: 2; //块元素显示的文本行数
		-webkit-box-orient: vertical;
		height: 45px;
		
		
	
	}
</style>
