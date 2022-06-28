<script>
    import TweetGalleryImage from './tweetGalleryImage.svelte'

    export let gallery = []
</script>

<div class="grid grid-cols-2 grid-rows-2 mt-2">
    {#if gallery?.length >= 4}
        <TweetGalleryImage src={gallery[0]} className="rounded-tl-xl"/>
        <TweetGalleryImage src={gallery[1]} className="rounded-tr-xl"/>
        <TweetGalleryImage src={gallery[2]} className="rounded-bl-xl"/>
        <TweetGalleryImage src={gallery[3]} className="rounded-br-xl"/>
    {/if}
    {#if gallery?.length === 3}
        <TweetGalleryImage src={gallery[0]} className="rounded-l-xl row-span-2 h-full"/>
        <TweetGalleryImage src={gallery[1]} className="rounded-tr-xl"/>
        <TweetGalleryImage src={gallery[2]} className="rounded-br-xl"/>
    {/if}
    {#if gallery?.length === 2}
        <TweetGalleryImage src={gallery[0]} className="rounded-l-xl row-span-2 h-full" square/>
        <TweetGalleryImage src={gallery[1]} className="rounded-r-xl row-span-2 h-full" square/>
    {/if}
    {#if gallery?.length === 1}
        <TweetGalleryImage src={gallery[0]} className="rounded-xl row-span-2 col-span-2" />
    {/if}
</div>