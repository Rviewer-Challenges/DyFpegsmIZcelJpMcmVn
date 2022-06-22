<script>

    const NAVIGATION_ITEM_TYPES = {
      ImageOnly: 'ImageOnly',
      Image: 'Image',
      FontIcon: 'FontIcon',
      Button: 'Button',
    }

    const navigationList = [
      {
        label: 'Twitter', type: NAVIGATION_ITEM_TYPES.ImageOnly, icon: 'https://cdn-icons-png.flaticon.com/512/733/733579.png', selected: true,
      },
      { label: 'Inicio', type: NAVIGATION_ITEM_TYPES.FontIcon, icon: 'e88a' },
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

<ul class="float-right w-1/2 cursor-default">
    {#each navigationList as navigationItem}
        <li class="m-5" class:fontBold="{navigationItem.selected === true}">
            {#if navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
                <img src={navigationItem.icon} alt={navigationItem.label} class="w-7">
            {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.Button}
                <button class="bg-sky-400 hover:bg-sky-500 rounded-full py-2 px-2 w-full">{navigationItem.label}</button>
            {:else}
                <button class="hover:bg-neutral-900 rounded-3xl inline py-2 px-2">
                    {#if navigationItem.type === NAVIGATION_ITEM_TYPES.Image || navigationItem.type === NAVIGATION_ITEM_TYPES.ImageOnly}
                        <img src={navigationItem.icon} alt={navigationItem.label} class="w-6">
                    {:else if navigationItem.type === NAVIGATION_ITEM_TYPES.FontIcon}
                        <span class="material-symbols-outlined align-middle"> {@html `&#x${navigationItem.icon}`} </span> 
                    {/if}
                    <span class="mx-4">{navigationItem.label}</span>
                </button>
            {/if}

        </li>
    {/each}
</ul>