<script>
  import NotoriousButton from '../../src/NotoriousButton5.svelte';

  let lastClicked = $state('');
</script>

<main>
  <h1>svelte-notoriousbutton</h1>
  <p>Svelte 5 example — all effects × both triggers</p>

  {#each ['sweep', 'glow', 'shake', 'pulse', 'border-sweep'] as effect}
    <section>
      <h2><code>{effect}</code></h2>
      <div class="row">
        <div class="card">
          <span class="tag">hover</span>
          <NotoriousButton
            label={effect}
            {effect}
            trigger="hover"
            onclick={() => (lastClicked = `${effect} / hover`)}
          />
        </div>
        <div class="card">
          <span class="tag">auto</span>
          <NotoriousButton
            label={effect}
            {effect}
            trigger="auto"
            onclick={() => (lastClicked = `${effect} / auto`)}
          />
        </div>
      </div>
    </section>
  {/each}

  <section>
    <h2>Custom style</h2>
    <div class="row">
      <NotoriousButton
        label="Danger"
        effect="shake"
        trigger="auto"
        style="background: #dc2626;"
        onclick={() => (lastClicked = 'danger')}
      />
      <NotoriousButton
        label="Pill"
        effect="sweep"
        trigger="hover"
        style="border-radius: 999px;"
        onclick={() => (lastClicked = 'pill')}
      />
      <NotoriousButton
        label="Large"
        effect="glow"
        trigger="auto"
        style="font-size: 1.25rem; padding: 0.8em 2em;"
        onclick={() => (lastClicked = 'large')}
      />
    </div>
  </section>

  {#if lastClicked}
    <p class="feedback">Last clicked: <strong>{lastClicked}</strong></p>
  {/if}
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: system-ui, sans-serif;
    background: #f1f5f9;
    color: #1e293b;
  }

  main {
    max-width: 640px;
    margin: 0 auto;
    padding: 2rem 1rem;
  }

  h1 {
    font-size: 1.75rem;
    margin-bottom: 0.25rem;
  }

  h2 {
    font-size: 1rem;
    color: #475569;
    margin-bottom: 0.75rem;
  }

  section {
    margin-top: 2rem;
  }

  .row {
    display: flex;
    gap: 1.5rem;
    flex-wrap: wrap;
  }

  .card {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.4rem;
  }

  .tag {
    font-size: 0.72rem;
    font-family: monospace;
    background: #e2e8f0;
    color: #475569;
    padding: 0.1em 0.5em;
    border-radius: 4px;
  }

  .feedback {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: #64748b;
  }
</style>
