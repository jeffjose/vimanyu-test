<script context="module" lang="ts">
	export async function load({ fetch }) {
		let res = await fetch('/gallery.json');

		if (res.ok) {
			return {
				props: {
					images: await res.json()
				}
			};
		}
		return {
			status: res.status,
			error: new Error()
		};
	}
</script>

<script lang="ts">
	import Image from '$lib/Image.svelte';

	export let images = [];
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div class="container">
	{#each images as image}
		<Image image={image.image} name={image.name} price={image.price} />
	{/each}
</div>

<style>
	.container {
		display: flex;
		column-gap: 10px;
	}

	.foo {
		color: red;
	}
</style>
