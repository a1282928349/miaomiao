<template>
	<div>
		<ul>
			<router-link to="/cinema" tag="li" activeClass="active">全城<i class="iconfont icon-lower-triangle"></i></router-link>
			<router-link to="/cinema" tag="li" activeClass="active">品牌<i class="iconfont icon-lower-triangle"></i></router-link>
			<router-link to="/cinema" tag="li" activeClass="active">特色<i class="iconfont icon-lower-triangle"></i></router-link>
		</ul>
	</div>
</template>

<script>
</script>

<style lang="scss" scoped>
	.active{
		// color: sandybrown;
		// border-bottom: 3px solid sandybrown;
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
