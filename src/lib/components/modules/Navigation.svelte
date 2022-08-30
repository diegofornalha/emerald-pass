<script>
  import { navItems } from "$lib/config/config";

  export let gap = "3em";
  export let color = "var(--clr-primary-main)";
</script>

<ul style={`gap: ${gap}`}>
  {#each navItems as navItem}
    <li>
      <a
        href={navItem.route}
        sveltekit:prefetch={navItem.prefetch}
        target={navItem.target}
        style={`color: ${color}`}>
        {navItem.title}
      </a>
    </li>
  {/each}
  <slot />
</ul>

<style type="scss">
  @use "../../styles/abstracts" as *;

  ul {
    display: flex;
    flex-direction: inherit;
    list-style-type: none;
    padding: 0;
    margin: 0;
    font-family: var(--font-mono);
    text-align: inherit;
    justify-content: inherit;
    align-items: inherit;
  }

  li {
    font-size: var(--fs-400);

    @include mq(medium) {
      font-size: var(--fs-300);
    }
  }

  a {
    text-decoration: none;
    transition: 0.3s;
  }
  a:hover {
    color: var(--clr-accent-strong);
  }
</style>
