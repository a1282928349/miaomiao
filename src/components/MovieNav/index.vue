<template>
	<div>
		<ul>
			<router-link to="/movie/city" tag="li" class="city">大连<i class="iconfont icon-lower-triangle"></i></router-link>
			<router-link to="/movie/nowplaying" activeClass="active" tag="li">正在热映</router-link>
			<router-link to="/movie/commingsoon" activeClass="active" tag="li">即将上映</router-link>
			<router-link to="/movie/search"tag="li" class="sousuo"><i class="iconfont icon-sousuo"></i></router-link>
		</ul>
	</div>
</template>

<script>
</script>

<style lang="scss" scoped>
	.active{
		color: sandybrown;
		border-bottom: 3px solid sandybrown;
	}
	ul{
		display: flex;
		border-bottom: 1px solid #C0CCDA;
		li{
			position: relative;
			flex: 1px;
			line-height: 50px;
			text-align: center;
			top: 0px;
		}
	}
	a{
		text-decoration: none;
	}
	.fixed{   //吸顶
		position: fixed;
		left: 0px;
		top: 0px;
		width: 100%;
		height: 40px;
		background-color: white;
		
	}
	.sousuo{
		color: red;
		i{
			font-size: 28px;
		}
	}
</style>
