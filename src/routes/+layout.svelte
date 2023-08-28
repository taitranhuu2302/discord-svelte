<script>
    import Sidebar from '$lib/components/Sidebar.svelte';
    import './styles.css';
</script>

<div class="app">
	<Sidebar/>
	<div class="tab"></div>
	<main>
		<slot/>
	</main>
</div>

<style lang="postcss">
    .app {
        @apply flex bg-[#313338] text-white h-screen;
    }

    .tab {
        @apply bg-[#2b2d31] w-[240px];
    }
</style>
