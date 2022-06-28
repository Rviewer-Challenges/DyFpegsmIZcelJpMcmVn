<script>
    import TweetButton from './TweetButton.svelte'
    import TweetIcon from './TweetIcon.svelte'

    export let className = ''

    const NAVIGATION_ITEM_TYPES = {
      ImageOnly: 'ImageOnly',
      Image: 'Image',
      FontIcon: 'FontIcon',
      Button: 'Button',
    }

    const navigationList = [
      {
        label: 'Twitter', type: NAVIGATION_ITEM_TYPES.ImageOnly, icon: 'https://cdn-icons-png.flaticon.com/512/733/733635.png',
      },
      {
        label: 'Inicio', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e88a', mobile: true, selected: true,
      },
      {
        label: 'Explorar', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e9ef', mobileIcon: 'e8b6', mobile: true,
      },
      {
        label: 'Notificaciones', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e7f4', mobile: true,
      },
      {
        label: 'Mensajes', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e158', mobile: true,
      },
      { label: 'Guardados', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e866' },
      { label: 'Listas', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e0ee' },
      { label: 'Perfil', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'f0d3' },
      { label: 'Más Opciones', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e619' },
      { label: 'Twittear', type: NAVIGATION_ITEM_TYPES.Button, icon: 'https://cdn-icons-png.flaticon.com/512/44/44870.png' },
    ]
</script>

<section class="{className}">
    <ul class="flex outline-none border-zinc-600 border-t sm:border-t-0 flex-row sm:flex-col cursor-default">
        {#each navigationList as navigationItem}
            <li class="py-1 {navigationItem.mobile ? 'grow text-center sm:text-left' : 'shrink'}  {navigationItem.selected ? 'font-bold' : ''}">
                {#if navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
                    <button class="hover:bg-sky-900/25  w-12 aspect-square p-3 ml-3 rounded-full {navigationItem.mobile ? 'inline' : 'hidden sm:inline'}">
                        <img src={navigationItem.icon} alt={navigationItem.label} class="w-7 grayscale invert">
                    </button>
                {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.Button}
                    <TweetButton className="w-56 h-12 hidden xl:inline" value={navigationItem.label}/>
                    <button class="hover:bg-sky-400 bg-sky-500 w-12 aspect-square p-2 ml-3 rounded-full self-center absolute bottom-20 right-5 sm:static sm:inline xl:hidden">
                        <img src={navigationItem.icon} alt={navigationItem.label} class="w-7 grayscale invert">
                    </button>
                {:else}
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
                {/if}
            </li>
        {/each}
    </ul>
</section>