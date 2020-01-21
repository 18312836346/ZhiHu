<template>
	<div>
			<div class="topic-head">
				<img  class="pic-all" src="../assets/image/special.png" />
				<span class="SpecialListPage-title">全部专题</span>
				<span class="SpecialListPage-count">共有489个专题</span>
			</div>
			
			<div class="container">
				<div class="row" v-for="(item,index) in specials" :key="index">
					<div class="left"><img :src="item.banner" alt=""></div>
					<div class="right">
						<div class="w-row">
							<h3 style="white-space:nowrap; overflow:hidden; text-overflow:ellipsis;">{{item.title}}</h3>
							<button class="button"><h4>关注专题</h4></button></div>
						
						<p class="meta">{{item.updated}}更新·{{item.viewCount}}次浏览</p>
						<p class="introduction">{{item.introduction}}</p>
						<!--显示标签类型-->
						<span v-for="(section,index) in item.sections" :key="index" class="section">
							{{section.sectionTitle}}
						</span>
						
					</div>
				</div>
			</div>
		</div>
</template>

<script>
	export default{
		name:'hot',
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
	@font-face {
		font-family: 'iconfont'; /* project id 1616266 */
		src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot');
		src: url('//at.alicdn.com/t/font_1616266_b8gknsgz736.eot?#iefix') format('embedded-opentype'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff2') format('woff2'),
			url('//at.alicdn.com/t/font_1616266_b8gknsgz736.woff') format('woff'), url('//at.alicdn.com/t/font_1616266_b8gknsgz736.ttf') format('truetype'),
			url('//at.alicdn.com/t/font_1616266_b8gknsgz736.svg#iconfont') format('svg');
	}
	
	.topic-head{
		background-color: rgb(255,255,255);
		height: 80px;
		margin-top: 1px;
		
	}
	
	.container{
		display: block;
		margin: auto;
		width: 60%;
		margin-top: 15px;
		
		}
		.row{background-color: rgb(255,255,255);
			display: flex;
			height: 200px;
			margin: 15px;
			border-radius: 10px;
		}
		.left{
			width: 40%;
			
			text-align: center;
		}
		.left img{
			width: 90%;
			margin-top: 25px;
			height: 150px;
			border-radius: 10px;
			
			
		}
		.right{
			margin-top: 20px;
			width: 60%;
			margin-right: 20px;
		}
		.w-row h3{
			width: 80%;
			
		}
		.button{
			width: 100px;
			border: none;
			background-color: rgb(235,245,255);
			color: rgb(30,134,255);
			height: 40px;
			border-radius: 5px;
			position: absolute;
			left: 1080px;
			}
		.meta{
			margin-top: 5px;
			color: darkgray;
			font-size: 12px;
		}
		.introduction{
			margin-top: 10px;
			margin-bottom: 10px;
			text-overflow: -o-ellipsis-lastline;
			overflow: hidden;
			text-overflow: ellipsis;
			display: -webkit-box;/*重点，不能用block等其他*/
			-webkit-line-clamp: 2;/*重点IE和火狐不支持*/
			-webkit-box-orient: vertical;/*重点*/
		}
		.section{
			float: left;
			background-color: rgb(246,246,246);
			width: auto;
			margin-right: 10px;
			padding: 2px;
			font-size: 13px;
			border-radius: 5px;
			height: auto;
		}
	
		
</style>