<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
  export let id;
  export let title;
  export let price;
  export let bestSeller = false;
  function addToCart() {
    dispatch('add-to-cart', { id: 'p1' });
  }
</script>

<article>
  <h1>{title}</h1>
  <h2>${price}</h2>
  {#if bestSeller}
    <h3>Best Sella!</h3>
  {/if}
  <button on:click="{addToCart}">Add to Cart</button>
  <button on:click="{() => dispatch('delete', 'p1')}">Delete</button>
</article>