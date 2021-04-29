<script>
  export let status;
  export let error;
</script>

<svelte:head>
  <title>Error - {status}</title>
</svelte:head>

{#if status !== 404}
  <div class="container">
    <article class="message is-danger" />
    <div class="message-header">
      <p>Error</p>
    </div>

    <div class="message-body">
      {error.message}
      <a href="/">Click here</a> to go back home.
    </div>
  </div>
{/if}

{#if status === 404}
  <div class="container">
    <article class="message is-danger" />
    <div class="message-header">
      <p>Page Not Found</p>
    </div>

    <div class="message-body">
      <a href="/">Click here</a> to go back home.
    </div>
  </div>
{/if}

<style>
  .container {
    margin: 40px;
  }
</style>
