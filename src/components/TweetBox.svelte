<script>
    import TweetBoxItem from './TweetBoxItem.svelte'
    
    export let boxData = {
      name: 'Tweet box',
      items: [
        {
          topic: 'Topic', name: '#Name', tweets: 0, image: '',
        },
      ],
    }
</script>

<section class="rounded-xl mt-4 bg-zinc-900">
    <h1 class="text-xl font-extrabold py-3 mx-4">{boxData.name}</h1>
    <ul class="w-full cursor-pointer">
        {#each boxData.items as boxItem}
            <TweetBoxItem boxItem={boxItem}/>
        {/each}
        <li class="h-12 py-2 px-4 hover:bg-zinc-800 rounded-b-xl">
            <a class="text-sky-500 text-sm" href="/" on:click={(e) => { e.preventDefault() }}>Mostrar más</a>
        </li>
    </ul>

</section>

<footer class="text-zinc-500 text-xs p-2">
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Condiciones de Servicio</a>
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Política de Privacidad</a>
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Política de cookies</a>
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Accesibilidad</a>
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Información de anuncios</a>
    <a class="pr-1 hover:underline whitespace-nowrap" href="/" on:click={(e) => { e.preventDefault() }}>Más opciones</a>
    <span class="text-xs whitespace-nowrap">© 2022 Twitter, Inc.</span>
</footer>





