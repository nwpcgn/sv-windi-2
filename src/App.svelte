<script>
  import svelteLogo from "./assets/svelte.svg";
  import Button from "./lib/md/Button.svelte";
</script>

<main>
  <section class="page">
    <div class="container mx-auto px-4">
      <header class="flex">
        <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
          <img src="/vite.svg" class="logo" alt="Vite Logo" />
        </a>
        <a href="https://svelte.dev" target="_blank" rel="noreferrer">
          <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
        </a>
      </header>
      <article class="nwp-prose">
        <h1>Header</h1>
        <h2>Vite + Svelte</h2>
        <h4>Nwp-Studio</h4>
        <p>
          Check out <a
            href="https://github.com/sveltejs/kit#readme"
            target="_blank"
            rel="noreferrer">SvelteKit</a
          >
          , the official Svelte app framework powered by Vite!
        </p>

        <p class="read-the-docs">
          Click on the Vite and Svelte logos to learn more
        </p>
      </article>
    </div>
  </section>
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
</style>
