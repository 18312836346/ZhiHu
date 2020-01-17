<template>
	<div>
<span style="color: #8590A6;font-size: 15px;">热榜</span>	</div>
</template>

<script>
	export default {
		name: 'hot',
		data() {
			return {
				specials: []
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/special/all').then(res => {
				console.log(res);
				this.specials = res.data.data;
			});
		}
	};
</script>

<style lang="scss" scoped>
</style>
