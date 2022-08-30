<div class="background-gradient" />

<style>
  .background-gradient {
    background: radial-gradient(
        ellipse at right,
        var(--clr-primary-main-t1),
        transparent
      ),
      radial-gradient(
        ellipse at bottom,
        var(--clr-primary-main-t7),
        transparent
      );
    backdrop-filter: blur(200px);
    height: 100%;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
  }
</style>
