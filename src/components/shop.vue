<template>
	<div>
		<h1>vuex-shopCart</h1>
		<div class="shop-listbox">
			<shop-list/>
		</div>
		<h2>已选商品</h2>
		<div class="shop-cartbox">
			<shop-cart/>
		</div>
	</div>
</template>

<script>

	import shopList from "./shop-list";
	import shopCart from './shop-cart';

	export default{
		name:'shop',
		components:{
			'shop-list':shopList,
			'shop-cart':shopCart
		}

	}
</script>