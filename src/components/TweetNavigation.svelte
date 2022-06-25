<script>
    import TweetButton from './TweetButton.svelte'
    import TweetIcon from './TweetIcon.svelte'

    const NAVIGATION_ITEM_TYPES = {
      ImageOnly: 'ImageOnly',
      Image: 'Image',
      FontIcon: 'FontIcon',
      Button: 'Button',
    }

    const navigationList = [
      {
        label: 'Twitter', type: NAVIGATION_ITEM_TYPES.ImageOnly, icon: 'https://cdn-icons-png.flaticon.com/512/733/733579.png',
      },
      {
        label: 'Inicio', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e88a', selected: true,
      },
      { label: 'Explorar', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e9ef' },
      { label: 'Notificaciones', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e7f4' },
      { label: 'Mensajes', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e158' },
      { label: 'Guardados', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e866' },
      { label: 'Listas', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e0ee' },
      { label: 'Perfil', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'f0d3' },
      { label: 'Más Opciones', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e619' },
      { label: 'Twittear', type: NAVIGATION_ITEM_TYPES.Button },
    ]
</script>

<section class="relative w-2/5 float-right">
    <ul class="cursor-default fixed">
        {#each navigationList as navigationItem}
            <li class="py-1 {navigationItem.selected ? 'font-bold' : ''}">
                {#if navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
                    <button class="hover:bg-sky-900/25 p-3 rounded-full">
                        <img src={navigationItem.icon} alt={navigationItem.label} class="w-7 grayscale brightness-200 contrast-200">
                    </button>
                {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.Button}
                    <TweetButton className="w-full py-3 " value={navigationItem.label}/>
                {:else}
                    <button class="hover:bg-neutral-900 rounded-3xl inline py-1.5 px-3">
                        {#if navigationItem.type === NAVIGATION_ITEM_TYPES.Image || navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
                            <img src={navigationItem.icon} alt={navigationItem.label} class="w-6">
                        {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.FontIcon}
                            <TweetIcon icon={navigationItem.icon} className="align-middle pb-1 pl-1 text-3xl" variation={navigationItem.selected ? 'rounded' : 'outlined'}/>
                        {/if}
                        <span class="mx-4 text-xl">{navigationItem.label}</span>
                    </button>
                {/if}
            </li>
        {/each}
    </ul>
</section>