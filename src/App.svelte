<script>
	import Fruits from './Frutis.svelte';
	import Parent from './Parent.svelte';
	import { storeName } from './store/store.js';
	let name = 'WORLD';
	storeName.set(name);
	let fruits = ['Apple', 'Banana', 'Cherry', 'Mango', 'Orange'];
</script>

<main>
	<Fruits {fruits}/>
	<Fruits {fruits} reverse />
	<Fruits {fruits} slice="0, 3" />

	<Parent />
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>