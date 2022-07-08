<script>
  import { goto } from "$app/navigation";
  import { onDestroy } from "svelte";
  import { fly } from "svelte/transition";
  import { store } from "../store";

  async function click() {
    setTimeout(() => {
      console.log("Set show to true");
      $store.show = true;
    }, 1000);
    await goto("other");
  }

  onDestroy(() => {
    console.log("On destroy called");
  });
</script>

<h1>Page 1</h1>

<button on:click={click}>Go to page 2</button>

{#if $store.show}
  <p transition:fly={{ y: 100, duration: 2000 }}>Peekaboo!</p>
{/if}
