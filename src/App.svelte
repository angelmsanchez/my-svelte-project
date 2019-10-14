<script>
  import Todos from "./components/Todos.svelte";
  import Nested from "./components/Nested.svelte";

  export let name;
</script>

<Nested answer={'answer'} />
<h1>Hello: {name}!!</h1>
<Todos />
