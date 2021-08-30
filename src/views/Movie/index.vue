<template>
  <div>
	  <movienav />
	  <router-view></router-view>
  </div>
</template>
<script>
import Vue from 'vue'
import movienav from '@/components/MovieNav'
import nowplaying from '@/components/NowPlaying'
export default {
    name: 'Movie',
	components:{
		movienav,nowplaying
	}
}
</script>

<style lang="sass" scoped>

</style>