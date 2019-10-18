<script>
  import Todos from "./components/Todos.svelte";
  import Nested from "./components/Nested.svelte";
  import Counter from "./components/Counter.svelte";
  import Inner from "./components/Inner.svelte";

  let name;
  let user = { loggedIn: false };
  let things = [
    { id: 1, color: "#0d0887" },
    { id: 2, color: "#6a00a8" },
    { id: 3, color: "#b12a90" },
    { id: 4, color: "#e16462" },
    { id: 5, color: "#fca636" }
  ];
  let m = { x: 0, y: 0 };

  function toggle() {
    user.loggedIn = !user.loggedIn;
  }

  function handleMousemove(event) {
    m.x = event.clientX;
    m.y = event.clientY;
  }

  function handleMessage(event) {
    alert(event.detail.text);
  }
</script>

<Counter />
<Inner on:message={handleMessage} />
<h1>Hello: {name}!!</h1>
<Nested answer={'answer'} />
<Nested />
<Todos />
{#each things as thing (thing.id)}
  <p>
    <span style="background-color: {thing.color}">initial</span>
  </p>
{/each}

{#if user.loggedIn}
  <button on:click={toggle}>Log out</button>
{/if}

{#if !user.loggedIn}
  <button on:click={toggle}>Log in</button>
{/if}

<div on:mousemove={handleMousemove}>The mouse position is {m.x} x {m.y}</div>
