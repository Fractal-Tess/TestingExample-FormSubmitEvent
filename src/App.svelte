<script>
  import svelteLogo from './assets/svelte.svg';
  import Counter from './lib/Counter.svelte';

  let showFormSuccess = false;
</script>

<main>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank"
      >SvelteKit</a
    >, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">Click on the Vite and Svelte logos to learn more</p>

  <h1>Here is the form!</h1>
  <form
    on:submit|preventDefault={() => {
      showFormSuccess = true;
    }}
  >
    <input type="text" placeholder="just a placehodler" />
    <input type="text" placeholder="just a placehodler" />
    <p>Uncomment the button out or remove the button</p>
    <!-- All of these should work, but can we do it without a button? -->
    <button>Submit</button>
    <!-- <button class="hidden">This button show be hidden</button> -->
    <!-- <button class="budget-hidden" /> -->
  </form>
  {#if showFormSuccess}
    <h1>The form fired succesfuly</h1>
  {/if}

  <a href="/">Reload page</a>
</main>

<style>
  .hidden {
    display: none;
  }

  .budget-hidden {
    width: 0;
    height: 0;
    position: absolute;
    outline: none;
    padding: 0;
    max-width: 0;
  }
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
