<script context="module">
    export let NAVIGATION_ITEM_TYPES = {
      ImageOnly: 'ImageOnly',
      Image: 'Image',
      FontIcon: 'FontIcon',
      Button: 'Button',
    }
</script>

<script>
    import TweetIcon from "../TweetIcon.svelte";

    export let navigationItem = {
      label: '', type: '', icon: '',
    }
</script>

<button class="hover:bg-neutral-900 rounded-3xl py-1.5 px-3 {navigationItem.mobile ? 'inline' : 'hidden sm:inline'}">
    {#if navigationItem.type === NAVIGATION_ITEM_TYPES.Image || navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
        <img src={navigationItem.icon} alt={navigationItem.label} class="w-6">
    {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.FontIcon}
        {#if navigationItem.mobileIcon}
            <TweetIcon icon={navigationItem.mobileIcon} className="align-middle pb-1 pl-1 text-3xl xl:hidden" variation={navigationItem.selected ? 'rounded' : 'outlined'}/>
            <TweetIcon icon={navigationItem.icon} className="align-middle pb-1 pl-1 text-3xl hidden xl:inline" variation={navigationItem.selected ? 'rounded' : 'outlined'}/>
        {:else}
        <TweetIcon icon={navigationItem.icon} className="align-middle pb-1 pl-1 text-3xl" variation={navigationItem.selected ? 'rounded' : 'outlined'}/>
        {/if}
    {/if}
    <span class="mx-4 text-xl hidden xl:inline">{navigationItem.label}</span>
</button>