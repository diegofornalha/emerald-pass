<script>
  import { Stack } from "$lib/components/atoms/index";
  import { dappTitle } from "$lib/config/config";
</script>

<a href="/">
  <Stack direction="row" gap="0.4em">
    <span>{dappTitle}</span>
  </Stack>
</a>

<style type="scss">
  a {
    text-decoration: none;

    span {
      font-family: var(--font-primary);
      font-size: 20px;
      color: var(--clr-primary-main);
      text-transform: uppercase;
      font-weight: 900;
      letter-spacing: 0.2ch;
      font-style: italic;
      background: linear-gradient(
        to left,
        var(--clr-primary-main),
        var(--clr-primary-main)
      );
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }
</style>
