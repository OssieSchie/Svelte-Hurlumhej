<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import Card from './lib/Card.svelte'
  let cards = []
  let value;
  function add(e){
    console.log(e);
    cards = cards.concat({header:value})
    value=""
  }
  // function addForm(e){
  //   console.log(e);
  //   cards
  // }
</script>

<main>
  <h1>Vite + Svelte</h1>
<!-- <Card header="svelte er for fedt"/> -->
{#each cards as card}
  <Card header={card.header}/>
{/each}

<!-- <button on:click={add}>Tilføj Card</button> -->
  
<form on:submit|preventDefault={add}>
  <input name="header" bind:value>
  <button>Tilføj Artikel</button>
</form>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
