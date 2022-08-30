<script>
  export let accent = false;
  export let error = false;
  export let border = false;
  export let hoverShadow = false;
  export let height = "100%";
  export let padding = "1.4rem";
  export let paddingInline;
  export let paddingBlock;

  let cardProps = {
    class: [$$restProps.class],
  };
</script>

<div
  class:accent
  class:error
  class:border
  class:hover-shadow={hoverShadow}
  style={`height: ${height}; padding: ${padding}; padding-inline: ${paddingInline}; padding-block: ${paddingBlock}`}
  {...cardProps}>
  <slot />
</div>

<style type="scss">
  div {
    background-color: var(--clr-primary-main-t9);
    border-radius: 1rem;
    padding: 1.4rem;
    width: 100%;
    transition: 0.5s;
  }
  .accent {
    background-color: var(--clr-primary-main-t7);
  }

  .border {
    border: 3px var(--clr-primary-main-t8) solid;
  }

  .hover-shadow:hover {
    box-shadow: var(--clr-primary-main) -7px 7px;
    transform: translateY(-4px);
  }
</style>
