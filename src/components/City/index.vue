<template>
	<div>
		<mt-index-list :style="{height: cityheight}">
		  <mt-index-section :index="data.index" v-for="data in datalist" :key="data.index">
			<mt-cell :title="city.name" v-for="city in data.city" :key="city.cityId"></mt-cell>
		  </mt-index-section>	
		</mt-index-list>
	</div>
</template>

<script>
import axios from 'axios'	

export default {
	name: 'city',
	data() {
		return {
			cityheight: 0,
			datalist: []
		}
	},
	mounted() {
		this.cityheight = 533+'px'
		
		axios({
			url: 'https://m.maizuo.com/gateway?k=3848435',
			headers: {
				'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"1629026349327559975796737"}',
				'X-Host': 'mall.film-ticket.city.list'
			}
		}).then(res=>{
			console.log(res.data)
			this.datalist = this.HandList(res.data.data.cities)
			console.log(this.datalist)
		})
	},
	
	methods:{
		HandList(data){
			var arr = [];
			for(var i=65; i<91;i++){
				arr.push(String.fromCharCode(i));
			}
			
			var list = []
			for(var i=0;i<arr.length;i++){
				var arry = data.filter(item=>item.pinyin.substring(0,1) === arr[i].toLowerCase())
				if(!(arry.length ===0)){
					list.push({
						index:arr[i],
						city:arry
					})
				}
			}
			return list;
		}
	}
}
</script>

<style>
</style>
