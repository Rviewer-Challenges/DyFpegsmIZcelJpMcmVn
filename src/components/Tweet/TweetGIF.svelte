<script>
    export let gif = {
      src: '',
      poster: '',
    }

    let toggleVideo = true

    function onToggleVideo() {
      toggleVideo = !toggleVideo
    }
</script>


<section class="relative">
    {#if toggleVideo}
        <img src={gif.poster} alt="" class="rounded-2xl" on:click={onToggleVideo}/>
    {:else}
        <video preload="auto" playsinline src={gif.src} alt="" poster={gif.poster} class="rounded-2xl" autoplay loop on:click={onToggleVideo}/>
    {/if}
    <span class="bg-zinc-700 w-8 text-sm text-white font-bold rounded absolute bottom-3 left-3 text-center" on:click={onToggleVideo}>GIF</span>
</section>