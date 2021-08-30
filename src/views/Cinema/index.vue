<template>
  <div>
	  <cinema></cinema>
	  <router-view></router-view>
	  <div class="cinema_container" :style="{height:cinameheight}">
	  	<ul>
	  		<li v-for="data in datalist" :key="data.cinemaId">
	  			{{data.name}}
	  		</li>
	  	</ul>
	  </div>
  </div>
</template>
<script>
import Vue from 'vue'
import cinema from '@/components/CinemaNav'
import axios from 'axios'
import BetterScroll from 'better-scroll'

export default {
    name: 'Cinema',
	data() {
		return {
			datalist:[],
			cinameheight: '0px'
		}
	},
	mounted() {
			this.cinameheight = document.documentElement.clientHeight-135 + 'px';
			axios({
				url: 'https://m.maizuo.com/gateway?cityId=310100&ticketFlag=1&k=5176696',
				headers:{
					'X-Client-Info': '{"a":"3000","ch":"1002","v":"5.0.4","e":"1629026349327559975796737","bc":"310100"}',
					'X-Host': 'mall.film-ticket.cinema.list'
				}
			}).then(res=>{
				this.datalist = res.data.data.cinemas
				this.$nextTick(()=>{
					var myscroll = new BetterScroll('.cinema_container',{  // 滚动
							scrollbar:{
							fade:true,
							interactive:false
							},
							pullUpLoad:{
								threshold: 50
							}
					});
					myscroll.on('pullingUp',()=>{
						console.log('到底了')
						this.datalist.push({
							cinemaId: '42351322',
							name: 'vip私人影院'
						})
						myscroll.refresh();
					})
				})
			})
	},
	components:{
		cinema
	}
}
</script>

<style lang="scss" scoped>
	.cinema_container{
		overflow: hidden;
		position: relative;
	}
</style>
