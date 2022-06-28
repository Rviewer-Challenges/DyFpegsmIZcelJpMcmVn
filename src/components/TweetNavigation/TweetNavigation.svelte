<script>
    import TweetNavigationIconItem, { NAVIGATION_ITEM_TYPES } from './TweetNavigationIconItem.svelte'
    import TweetNavigationImageItem from './TweetNavigationImageItem.svelte'
    import TweetNavigationButtonItem from './TweetNavigationButtonItem.svelte'

    export let className = ''

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
                    <TweetNavigationImageItem navigationItem={navigationItem}/>
                {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.Button}
                    <TweetNavigationButtonItem navigationItem={navigationItem}/>
                {:else}
                    <TweetNavigationIconItem navigationItem={navigationItem}/>
                {/if}
            </li>
        {/each}
    </ul>
</section>