<script>
    import TweetAvatar from '../TweetAvatar.svelte'
    import TweetIcon, { Icons } from '../TweetIcon.svelte'
    import TweetIconButton from '../TweetIconButton.svelte'

    import TweetText from './TweetText.svelte'
    import TweetGallery from './TweetGallery.svelte'
    import TweetGIF from './TweetGIF.svelte'
    import TweetLinkImage from './TweetLinkImage.svelte'
    import TweetImage from './TweetImage.svelte'
    import TweetActions from './TweetActions.svelte'

    export let tweet = {
      userId: '',
      userName: '',
      userImage: '',
      timeAgo: '1m',
      comments: 0,
      retweets: 0,
      likes: 0,
    }
</script>

<section class="flex flex-row py-4 pl-4 border-b border-zinc-700 cursor-pointer hover:bg-zinc-900/50">
    <span class="shrink">
       <TweetAvatar src={tweet.userImage}/>
    </span>
    <section class="grow flex flex-col ml-4">
        <header class="flex flex-row relative">
            <span class="font-bold text-base hover:underline">{tweet.userName}</span>
            {#if tweet.verified}
                <TweetIcon icon={Icons.Verified} className="text-lg ml-1" variation='rounded'/>
            {/if}
            <span class="px-2 py-1 text-zinc-400/80 text-sm">@{tweet.userId} · {tweet.timeAgo}</span>
            <TweetIconButton icon={Icons.MoreHorizontal} size="sm" className="text-sm absolute right-2 -top-1 text-zinc-500 hover:bg-sky-900/25 hover:text-sky-500"/>
        </header>
        <section class="mr-4 mt-2">
            {#if tweet.summary}
                <TweetText text={tweet.summary}/>
            {/if}
            {#if tweet.image}
                <TweetImage src={tweet.image}/>
            {/if}
            {#if tweet.video}
                <TweetGIF gif={tweet.video}/>
            {/if}
            {#if tweet.gallery}
                <TweetGallery gallery={tweet.gallery}/>
            {/if}
            {#if tweet.linkImage}
                <TweetLinkImage linkImage={tweet.linkImage}/>
            {/if}
        </section>
        <TweetActions tweet={tweet}/>
    </section>
</section>
