<script>
    import IconButton from "$lib/components/IconButton.svelte";
    import IconDiscord from "$lib/icons/IconDiscord.svelte";
    import IconAdd from "$lib/icons/IconAdd.svelte";
    import IconExplore from "$lib/icons/IconExplore.svelte";
    import IconDownload from "$lib/icons/IconDownload.svelte";
</script>

<section class="sidebar">
	<IconButton tooltip="Direct Messages" hoverColor="#5865f2">
		<IconDiscord slot="icon"/>
	</IconButton>
	<div class="line"></div>
	<IconButton hoverColor="#23a559" hoverTextColor="#fff" tooltip="Add a Server">
		<IconAdd slot="icon"/>
	</IconButton>
	<IconButton hoverColor="#23a559" hoverTextColor="#fff" tooltip="Explore Discoverable Servers">
		<IconExplore slot="icon"/>
	</IconButton>
	<div class="line"></div>
	<IconButton hoverColor="#23a559" hoverTextColor="#fff" tooltip="Download Apps">
		<IconDownload slot="icon"/>
	</IconButton>
</section>

<style lang="postcss">
    .sidebar {
        @apply min-w-[72px] bg-[#1e1f22] pt-[12px] flex flex-col items-center gap-[8px] relative;
    }

    .line {
        @apply h-[2px] w-[32px] rounded-[1px] bg-[#35363c];
    }
</style>