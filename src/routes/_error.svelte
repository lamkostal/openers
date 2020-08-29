<script>
	
	

	
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
    .error-message h1{
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

<div class="error-message">
    <h1>404, not found</h1>
    <h2>hmm, something went wrong here</h2>
    <a href="/">back to homepage</a>
</div>
