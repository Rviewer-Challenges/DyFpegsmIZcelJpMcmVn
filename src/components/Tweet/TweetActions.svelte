<script>
    import { Icons } from '../TweetIcon.svelte'
    import TweetIconButton from '../TweetIconButton.svelte'

    export let tweet = {
      comments: 0,
      retweets: 0,
      likes: 0,
    }
    
</script>

<span class="flex flex-row mt-2 justify-between w-3/4">
    <div class="flex flex-row">
        <TweetIconButton icon={Icons.ChatBubble} className="text-zinc-500 hover:bg-sky-900/25 hover:text-sky-500 peer" iconClassName="text-xl" size="sm"/>
        <span class="text-xs pl-1 pt-2.5 text-zinc-500 peer-hover:text-sky-500 cursor-default">{tweet.comments || ''}</span>
    </div>
    <div class="flex flex-row">
        <TweetIconButton icon={Icons.Repeat} className="text-zinc-500 hover:bg-sky-900/25 hover:text-emerald-500 peer" iconClassName="text-xl" size="sm"/>
        <span class="text-xs pl-1 pt-2.5 text-zinc-500 peer-hover:text-emerald-500 cursor-default">{tweet.retweets || ''}</span>
    </div>
    <div class="flex flex-row">
        <TweetIconButton icon={Icons.Favorite} className="text-zinc-500 hover:bg-sky-900/25 hover:text-rose-500 peer" iconClassName="text-xl" size="sm"/>
        <span class="text-xs pl-1 pt-2.5 text-zinc-500 peer-hover:text-rose-500 cursor-default">{tweet.likes || ''}</span>
    </div>
    <TweetIconButton icon={Icons.FileUpload} className="text-zinc-500 hover:bg-sky-900/25 hover:text-sky-500 peer" iconClassName="text-xl" size="sm"/>
</span>