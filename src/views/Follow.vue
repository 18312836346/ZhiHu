<template>
	<div>
<span style="color: #8590A6;font-size: 15px;">关注</span>		</div>
</template>

<script>
	export default{
		name:'follow',
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

<style>
</style>