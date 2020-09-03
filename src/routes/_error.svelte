<script>
	
	
  export let status;
  export let error;

  const dev = process.env.NODE_ENV === 'development';
	
</script>

<style>
	.error-message{
        position: relative;
        background-color: var(--inv-main-text-color);
        opacity: 0.9;
        color:var(--main-color);
        display:flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width:100%;
        height: 100vh;
        text-align: center;
        z-index: 10;
    }
     h1{
        font-size: 6em;
        font-family: "Dancing Script";
    }
    h2{
        font-size: 1.5em;
    }
</style>

<svelte:head>
	<title>error 404</title>
</svelte:head>
{#if status === 404}
<h1>404 not found</h1>
  
{:else}
  <h1>Error: {error.message}</h1>
  <p>status: {status}</p>
  {#if dev && error.stack}
    <pre>{error.stack}</pre>
  {/if}
{/if}

<div class="error-message">
    <h2>hmm, something went wrong here</h2>
    <a href="/">back to homepage</a>
</div>
