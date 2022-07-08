<script>
  import { goto } from "$app/navigation";
</script>

<h1>Page 2</h1>

<button on:click={() => goto("/")}>Go to page 1</button>
