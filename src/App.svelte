<script>
  import Todos from './components/Todos.svelte';

	export let name;

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}!</h1>
<Todos />
