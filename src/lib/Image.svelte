<script lang="ts">
	export let name;
	export let price;
	export let image;
</script>

<div class="image">
	{image}
	<img src={image} />
	<span class="name">{name}</span>
	<span class="price">{price} ETH</span>
</div>

<style>
	.image {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.name {
		color: #333;
	}

	.price {
		color: green;
	}
</style>
