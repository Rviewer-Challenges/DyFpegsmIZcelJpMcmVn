<script>
  import TweetFeedInput from '../components/TweetFeedInput.svelte'
  import Tweet from '../components/Tweet/Tweet.svelte'
  import { Icons } from '../components/TweetIcon.svelte'
  import TweetIconButton from '../components/TweetIconButton.svelte'
  import TweetAvatar from '../components/TweetAvatar.svelte'

  import tweets from '../mocks/tweets.json'

  export let className = ''

  const avatarSrc = 'https://pbs.twimg.com/profile_images/1470275753895997445/4te7URwk_400x400.jpg'
</script>

<section class="flex flex-col relative {className}">
    <header class="h-12 left-0 top-0 flex w-full backdrop-blur-lg sticky bg-zinc-900/75 p-1 z-10 cursor-pointer">
        <TweetAvatar src={avatarSrc} className="shrink mx-4 mt-1 sm:hidden" size='sm'/>
        <span class="shrink font-bold text-lg p-2 align-middle">
          Inicio
        </span>
        <div class="grow">
          <TweetIconButton icon={Icons.AutoAwesome} className="hover:bg-zinc-400/25 rotate-180 float-right"/>
        </div>
    </header>
    <TweetFeedInput className="shrink hidden sm:inline"/>
    <span class="h-13 text-center py-3 border-b border-zinc-700 hover:bg-zinc-900/50 cursor-pointer text-sky-400">Mostrar 7 Tweets</span>
    <ul class="grow">
        {#each tweets as tweet}
            <Tweet tweet={tweet}/>
        {/each}
    </ul>
</section>