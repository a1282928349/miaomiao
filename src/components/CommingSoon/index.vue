<template>
	<div>
		<ul>
			<li v-for="data in datalist.rows" :key="data.id">
				
				{{data.movie_name}}
				上映时间:{{data.movie_release_date}}
				主演:{{data.starring}}
				<el-button type="danger" disabled size='mini'>预约</el-button>
				<img :src="'http://127.0.0.1:8000/' + data.movie_poster" />
				
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
			url: 'http://127.0.0.1:8000/app/movies/anticipate_list/'
		}).then(res=>{
			this.datalist = res.data
			console.log(this.datalist.rows)
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
