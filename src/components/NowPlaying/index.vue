<template>
	<div>
		<ul>
			<li v-for="data in datalist.data" :key="data.id">
				<img :src="'http://127.0.0.1:8000/' + data.movie_poster" />
				{{data.movie_name}}
				观众评:{{data.movie_score}}
				主演:{{data.starring}}
				<el-button type="danger" disabled size='mini'>购票</el-button>
			</li>
		</ul>
	</div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'Nowplaying',
	data() {
		return{
			datalist: []
		}
	},
	mounted() {
		axios({
			url: 'http://127.0.0.1:8000/app/movies/showing_list/?select_type=0'
		}).then(res=>{
			this.datalist = res.data
			console.log(this.datalist.data)
		})
	},
	
}
</script>

<style lang="scss" scoped>
	img{
		height: 20%;
		width: 20%;
	}
</style>
