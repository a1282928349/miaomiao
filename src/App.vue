<template>
	<div>
		<Header></Header>
		<tabbar></tabbar>
		<router-view/>
	</div>
</template>

<script type="text/javascript">
import tabbar from '@/components/Tabbar'
import Header from '@/components/Header'

export default {
	components:{
		Header,tabbar
	}
}	
</script>
