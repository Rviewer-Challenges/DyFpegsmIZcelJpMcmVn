<script>
  import TweetFeedInput from '../components/TweetFeed/TweetFeedInput.svelte'
  import Tweet from '../components/Tweet/Tweet.svelte'
  import TweetFeedHeader from '../components/TweetFeed/TweetFeedHeader.svelte'

  import tweets from '../mocks/tweets.json'

  export let className = ''
</script>

<section class="flex flex-col relative {className}">
    <TweetFeedHeader/>
    <TweetFeedInput className="shrink hidden sm:inline"/>
    <span class="h-13 text-center py-3 border-b border-zinc-700 hover:bg-zinc-900/50 cursor-pointer text-sky-400">Mostrar 7 Tweets</span>
    <ul class="grow">
        {#each tweets as tweet}
            <Tweet tweet={tweet}/>
        {/each}
    </ul>
</section>