<script>
  import Product from "./Product.svelte";
  import CartItem from "./CartItem.svelte";

  let renderedComponent = CartItem;

  function toggle() {
    if (renderedComponent === CartItem) {
      return (renderedComponent = Product);
    }
    renderedComponent = CartItem;
  }
</script>

<button on:click={toggle}>Toggle</button>

<svelte:component this={renderedComponent} title={renderedComponent === CartItem ? "Another product" : "Test product"} id="p1" />
