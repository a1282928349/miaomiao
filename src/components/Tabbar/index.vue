
<template>
	<nav>
		<ul>
			<router-link to='/movie' tag="li" active-class="active"><i class="iconfont icon-dianying"></i>电影</router-link>
			<router-link to='/cinema' tag="li" active-class="active"><i class="iconfont icon-yingyuan"></i>影院</router-link>
			<router-link to='/mine' tag="li" active-class="active"><i class="iconfont icon-wode"></i>我的</router-link>
		</ul>
	</nav>
</template>

<script>
export default {
    name: 'Tabbar',
}
</script>
</script>

<style lang="scss" scoped>
	.active{
		color: darkorange;
	}
	
	nav{
		position: fixed;
		bottom: 0px;
		left: 0px;
		width: 100%;
		height: 40px;
		line-height: 40px;
		background-color: wheat;
		ul{
			display: flex;
			li{
				flex: 1;
				text-align: center;
				margin-left: 0px;
			}
		}
	}
	
</style>
