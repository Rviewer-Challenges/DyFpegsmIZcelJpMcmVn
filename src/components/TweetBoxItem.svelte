<script>
    import TweetIconButton from './TweetIconButton.svelte'
    import { Icons } from './TweetIcon.svelte'

    export let boxItem = {
      topic: 'Topic', name: '#Name', tweets: 0, image: '',
    }
</script>


<li class="h-18 flex flex-col justify-between py-2 px-4 hover:bg-zinc-800/50 relative">
    {#if boxItem.image}
        <div class="absolute right-4 top-2 rounded-lg w-16 h-16 bg-cover bg-center" style="background-image: url('{boxItem.image}')"/>
    {:else}
        <TweetIconButton icon={Icons.MoreHorizontal} size="sm" className="text-sm absolute right-2 top-2 text-zinc-500 hover:bg-sky-900/25 hover:text-sky-500"/>
    {/if}
    <span class="text-zinc-400/75 text-xs py-1">{boxItem.topic}</span>
    <span class="text-white text-sm font-semibold">{boxItem.name}</span>
    <span class="text-zinc-400/75 text-xs py-1">{`${boxItem.tweets} Tweets`}</span>
</li>