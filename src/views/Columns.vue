<template>
	<div>
		<div class="columns-top">
			<!-- 知乎文字 -->
			<a aria-label="知乎">
				<svg viewBox="0 0 200 91" class="zhihu" style="height:30px;width:64px" width="64" height="30" aria-hidden="true">
					<title>
					</title>
					<g>
						<path d="M53.29 80.035l7.32.002 2.41 8.24 13.128-8.24h15.477v-67.98H53.29v67.978zm7.79-60.598h22.756v53.22h-8.73l-8.718 5.473-1.587-5.46-3.72-.012v-53.22zM46.818 43.162h-16.35c.545-8.467.687-16.12.687-22.955h15.987s.615-7.05-2.68-6.97H16.807c1.09-4.1 2.46-8.332 4.1-12.708 0 0-7.523 0-10.085 6.74-1.06 2.78-4.128 13.48-9.592 24.41 1.84-.2 7.927-.37 11.512-6.94.66-1.84.785-2.08 1.605-4.54h9.02c0 3.28-.374 20.9-.526 22.95H6.51c-3.67 0-4.863 7.38-4.863 7.38H22.14C20.765 66.11 13.385 79.24 0 89.62c6.403 1.828 12.784-.29 15.937-3.094 0 0 7.182-6.53 11.12-21.64L43.92 85.18s2.473-8.402-.388-12.496c-2.37-2.788-8.768-10.33-11.496-13.064l-4.57 3.627c1.363-4.368 2.183-8.61 2.46-12.71H49.19s-.027-7.38-2.372-7.38zm128.752-.502c6.51-8.013 14.054-18.302 14.054-18.302s-5.827-4.625-8.556-1.27c-1.874 2.548-11.51 15.063-11.51 15.063l6.012 4.51zm-46.903-18.462c-2.814-2.577-8.096.667-8.096.667s12.35 17.2 12.85 17.953l6.08-4.29s-8.02-11.752-10.83-14.33zM199.99 46.5c-6.18 0-40.908.292-40.953.292v-31.56c1.503 0 3.882-.124 7.14-.376 12.773-.753 21.914-1.25 27.427-1.504 0 0 3.817-8.496-.185-10.45-.96-.37-7.24 1.43-7.24 1.43s-51.63 5.153-72.61 5.64c.5 2.756 2.38 5.336 4.93 6.11 4.16 1.087 7.09.53 15.36.277 7.76-.5 13.65-.76 17.66-.76v31.19h-41.71s.88 6.97 7.97 7.14h33.73v22.16c0 4.364-3.498 6.87-7.65 6.6-4.4.034-8.15-.36-13.027-.566.623 1.24 1.977 4.496 6.035 6.824 3.087 1.502 5.054 2.053 8.13 2.053 9.237 0 14.27-5.4 14.027-14.16V53.93h38.235c3.026 0 2.72-7.432 2.72-7.432z"
						 fill-rule="evenodd">

						</path>
					</g>
				</svg>
			</a>

			<!-- 写文章按钮 -->


			<button type="button" class="write-article">
				写文章</button>

		</div>

		<div class="k"></div>
		<div class="background">
			<img src="../assets/image/columns.png" style="margin: 0 auto; margin-left: -500px;" alt="">
		</div>
		<!-- 专栏发现 -->
		<div class="found" style="margin-top: 100px; background-image:url(../assets/image/background.png);">
			<div class="row3">
				<div class="row3-columns" v-for="(item, index) in columns" v-if="index>=begin&&index<=end" :key="index">
					<!-- 头像 -->

					<div class="columns-header" style="width: 70px; height: 70px;border-radius: 50%; overflow: hidden;margin:  0 auto; margin-top: 20px;">
						<img :src="item.imageUrl" alt="" style="width: 100%;" />
					</div>
					<!-- 标题 -->
					<div class="columnbs-title">
						<onbr>
							<h2><span style="color: #000000;">{{item.title}}</span></h2>
						</onbr>
					</div>
					<!-- 介绍 -->
					<div class="columnbs-description" style="height:44px; text-overflow: ellipsis; overflow: hidden;margin-top: 10px;text-align: center;">
						<onbr><span style="font-size: 14px;text-align: center;">{{item.description}}</span></onbr>
					</div>
					<!-- 关注与文章 -->
					<div class="cloumnbs-followers-articles_count">
						<span style="font-size: 13px; text-align: center; margin-top: 10px;">{{item.followers}}&nbsp;人关注&nbsp;|&nbsp;{{item.articlesCount}}&nbsp;篇文章</span>
					</div>


					<!-- 进入专栏按钮 -->

					<div class="columnbs-button" style="height: 35px;width:100px;margin: 0 auto; margin-top: 20px;">
						<!-- 关注按钮 -->
						<a v-bind:href="item.url" style="text-decoration: none;display:block;">
							<button class="button" style="height: 35px;width:100px;margin: 0 auto;border: 1px solid; border-color: #4CAF50;background-color: #FFFFFF;">
								<h4 style="color: #4CAF50;">进入专栏</h4>
							</button></a>
					</div>

				</div>
	                    <div style="margin-top: -100px;">
							<button class="refresh" @click="refresh()"><svg class="Zi Zi--Refresh Button-zi" fill="currentColor" viewBox="0 0 24 24" width="1.2em" height="1.2em"><path d="M20 12.878C20 17.358 16.411 21 12 21s-8-3.643-8-8.122c0-4.044 3.032-7.51 6.954-8.038.034-1.185.012-1.049.012-1.049-.013-.728.461-1.003 1.057-.615l3.311 2.158c.598.39.596 1.026 0 1.418l-3.31 2.181c-.598.393-1.08.12-1.079-.606 0 0 .006-.606-.003-1.157-2.689.51-4.675 2.9-4.675 5.708 0 3.21 2.572 5.822 5.733 5.822 3.163 0 5.733-2.612 5.733-5.822 0-.633.51-1.148 1.134-1.148.625 0 1.133.515 1.133 1.148" fill-rule="evenodd"></path></svg>
				换一换</button>
						</div>
			</div>

		</div>
	</div>

</template>

<script>
	export default {
		name: 'columns',
		data() {
			return {
				columns: [],
				begin:0,
				end:7,
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/columns/all').then(res => {
				console.log(res);
				this.columns = res.data.data;
			});
		},
		methods:{
			refresh(){
				if(this.end>=this.columns.length){
					this.begin=0;
					this.end=7;
				}
				else{
					this.begin +=8;
				     this.end +=8;
				}
			}
		}
	};
</script>
<style>
	.columns-top {
		background-color: #FFFFFF;
		height: 70px;
	}

	.zhihu {
		fill: #0084FF;
		margin-left: 250px;
		margin-top: 20px;
	}

	.write-article {
		margin-left: 770px;
		color: #0084ff;
		border-color: #0084ff;
		padding: 0 16px;
		font-size: 14px;
		line-height: 32px;
		text-align: center;
		background: none;
		border: 1px solid;
		border-radius: 3px;
	}

	.k {
		width: 1000px;
		height: 1px;
		margin-top: 2px;
	}

	.Popover {
		position: relative;
		display: inline-block;

	}

	.Popover img {
		margin-left: 10px;
	}

	.background {
		margin: 0 auto;
		width: 1000px;
		height: 600px;
		background: url("https://static.zhihu.com/heifetz/assets/patterns.c72a480c.png");
	}

	.found {
		.columns {
			display: block;
			margin: auto;
			width: 70%;
			margin-top: 15px;
		}
	}

	.row3 {
		margin-left: 300px;
		display: flex;
		flex-wrap: wrap;
		border-radius: 10px;
		width: 1000px;
		height: 1000px;
	}

	.row3-columns {
		box-shadow: 1px 3px 3px #aaa;
		width: 210px;
		margin: 15px;
		height: 290px;
		background-color: rgb(255, 255, 255);
		
	}

	.columnbs-title {
		height: auto;
		text-overflow: ellipsis;
		overflow: hidden;
		color: #000000;
		font-size: 15px;
		text-align: center;
		margin-left: -5px;
		margin-top: 15px;
	}

	.columnbs-description {

		text-overflow: ellipsis;
		overflow: hidden;
		color: #000000;
		font-size: 15px;
	}

	.refresh {
		border: 1px solid black;
		background-color: white;
		padding-top: 5px;
		padding-bottom: 5px;
		padding-left: 15px;
		padding-right: 15px;
		border-radius: 5px;
		margin: 20px;
		margin-left: 440px;

	}
</style>
