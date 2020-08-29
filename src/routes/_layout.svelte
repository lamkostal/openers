<script>
import Nav from "../components/Nav.svelte";
import Footer from "../components/Footer.svelte";



</script>

<style>
.layout{
	display:flex;
	flex-direction:column;
	justify-content: space-between;
}

</style>



<div class="layout">
<Nav/>

	<slot>

	</slot>
	<Footer/>
</div>
