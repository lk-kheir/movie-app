<script xmlns:svelte="http://www.w3.org/1999/html">
    import global from '../global.css'
    import NavBar from "../components/Nabvar.svelte";
</script>

<svelte:head>
    <title>MovieDB</title>
</svelte:head>

<NavBar />

<slot />