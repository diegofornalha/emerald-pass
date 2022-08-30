<script>
  export let address = "";
</script>

<span class="address">
  <slot />
  {address}
</span>

<style type="scss">
  .address {
    color: var(--clr-primary-main);
    background-color: var(--clr-primary-main-t9);
    font-size: var(--fs-200);
    font-weight: 500;
    padding: 0.2em 0.9em;
    border-radius: 0.5rem;
    width: fit-content;
    letter-spacing: 0.05em;
  }
</style>
