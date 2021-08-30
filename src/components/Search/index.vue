<template>
	<div id="app">
		<!-- <mt-search v-model="value"></mt-search> -->
	    <input type="text" placeholder="流浪地球" v-model='key_word' >
		<button @click="searchList(key_word)">搜索</button>
	    <ul v-if="searchResult.total != 0">
	        <li v-for="(item,index) in searchResult.rows" :key='item.id'>
					{{item.movie_name}}
				观众评:{{item.movie_score}}
				主演:{{item.starring}}
				<img :src="'http://127.0.0.1:8000/' + item.movie_poster " />
			</li>
	    </ul>
		<p v-else>暂无内容</p>
	</div>
</template>

<script>
	import axios from 'axios'
	export default {
		data() {
			return { 
				key_word: "",
				searchResult: [],
			}
		},
		methods: {
		    searchList: function(key_word){
				if(key_word == ''){
					alert('您还没有输入！！！')
					return
				}
				axios({
					method: 'get',
					url: 'http://127.0.0.1:8000/app/movies/movie_list/?key_word=' + key_word
				}).then(res=>{
					this.searchResult = res.data
					
				})
				
		    }
		}
	}
</script>

<style lang="scss" scoped>
	img{
		width: 20%;
		height: 20%;
	}
	input{
		width: 300px;
	}
</style>
