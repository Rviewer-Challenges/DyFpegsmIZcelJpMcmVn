<script>
    import TweetAvatar from '../components/TweetAvatar.svelte'
    import TweetIcon, { Icons } from '../components/TweetIcon.svelte'
    import TweetIconButton from '../components/TweetIconButton.svelte'

    import TweetFeedHeader from '../components/TweetFeedHeader.svelte'
    
    const tweets = [
      {
        userId: 'SergijeZ',
        userName: 'Sergio Guerra',
        userImage: 'https://pbs.twimg.com/profile_images/1470275753895997445/4te7URwk_400x400.jpg',
        video: {
          src: 'https://video.twimg.com/tweet_video/FV7D9ttXoAAK5S1.mp4',
          poster: 'https://pbs.twimg.com/tweet_video_thumb/FV7D9ttXoAAK5S1.jpg',
        },
        timeAgo: '2m',
        comments: 0,
        retweets: 0,
        likes: 0,
      },
      {
        userId: 'JavaScriptDaily',
        userName: 'JavaScript Daily',
        userImage: 'https://pbs.twimg.com/profile_images/1497227696438398981/zuPiHqzd_400x400.jpg',
        summary: 'Going to try tweeting using GitHub Copilot. It’s going well so far.. <br/><br/> // copyright 1998 © Sun Microsystems',
        timeAgo: '20m',
        comments: 6,
        retweets: 7,
        likes: 122,
      },
      {
        userId: 'MoureDev',
        userName: 'Brais Moure',
        userImage: 'https://pbs.twimg.com/profile_images/1539308966982860800/3UGtyag9_400x400.jpg',
        verified: true,
        summary: 'Aprender nuevos lenguajes de programación/frameworks/tecnologías está muy bien, pero... ¡Aprende inglés! <br/><br/> 1000 días seguidos dándole caña a <span class="text-sky-500 hover:underline">@duolingoespanol</span> 🤘  <br/><br/> ¿Cuál es tu método?',
        image: 'https://pbs.twimg.com/media/FV7IOEwWQAAJJFC?format=jpg&name=medium',
        timeAgo: '14m',
        comments: 1,
        retweets: 0,
        likes: 7,
      },
      {
        userId: 'Yumes_Japan',
        userName: 'Yumely Japanese Teacher🇯🇵',
        userImage: 'https://pbs.twimg.com/profile_images/1492387429625438211/yvGC2Is4_400x400.jpg',
        summary: '生(い) きる　live <br/><br/> 学生(がくせい)student <br/> 生憎(あいにく)unfortunately <br/> 生涯(しょうがい)lifetime <br/> 芝生(しばふ)lawn <br/> 生意気(なまいき)cheeky <br/> 再生(さいせい)playback <br/> 生計(せいけい)livelihood <br/> 一生(いっしょう)whole life <br/> 生卵(なまたまご)row egg <br/><br/> There are many ways to read 生😳',
        timeAgo: '21 jun.',
        comments: 2,
        retweets: 11,
        likes: 47,
      },
      {
        userId: '5eniorDeveloper',
        userName: 'El Programador Senior',
        userImage: 'https://pbs.twimg.com/profile_images/1529548668629667843/FcAurPhS_400x400.jpg',
        summary: 'Sí soy, y qué?',
        image: 'https://pbs.twimg.com/media/FV4t60gWQAczcxd?format=png&name=900x900',
        timeAgo: '10h',
        comments: 11,
        retweets: 53,
        likes: 558,
      },
      {
        userId: 'MoureDev',
        userName: 'Brais Moure',
        userImage: 'https://pbs.twimg.com/profile_images/1539308966982860800/3UGtyag9_400x400.jpg',
        verified: true,
        summary: 'Estamos revisando aplicaciones que ha creado la comunidad en directo desde Twitch!<br/><br/>¿Te vienes?<br/><br/>Es una gran manera de aprender y dar feedback a l@s devs',
        timeAgo: '21 jun.',
        comments: 3,
        retweets: 4,
        likes: 22,
      },
      {
        userId: 'Microsoft',
        userName: 'Microsoft',
        verified: true,
        userImage: 'https://pbs.twimg.com/profile_images/1454912483248930822/_hO4WPRC_400x400.png',
        summary: 'The perfect phone wallpaper? Something that mixes a little nostalgia with a modern flare. <span class="text-sky-500 hover:underline">#WallpaperWednesday</span>',
        timeAgo: '20m',
        gallery: [
          'https://pbs.twimg.com/media/FV4xXTLXoAEVOWF?format=jpg&name=900x900',
          'https://pbs.twimg.com/media/FV4xXpFXEAIBzvI?format=jpg&name=900x900',
          'https://pbs.twimg.com/media/FV4xYWXWIAEBJXF?format=jpg&name=900x900',
          'https://pbs.twimg.com/media/FV4xYAQXEAELbDD?format=jpg&name=900x900',
        ],
        comments: 6,
        retweets: 7,
        likes: 122,
      },
    ]

    let toggleVideo = true

    function onToggleVideo() {
      toggleVideo = !toggleVideo
    }
</script>

<section class="flex flex-col">
    <TweetFeedHeader className="shrink"/>
    <span class="h-12 text-center py-3 border-b border-zinc-700 hover:bg-zinc-900/50 cursor-pointer text-sky-400">Mostrar 7 Tweets</span>
    <ul class="grow">
        {#each tweets as tweet}
            <section class="flex flex-row py-4 pl-4 border-b border-zinc-700 cursor-pointer hover:bg-zinc-900/50">
                <span class="shrink">
                   <TweetAvatar src={tweet.userImage}/>
                </span>
                <section class="grow flex flex-col ml-4">
                    <header class="flex flex-row">
                        <span class="font-bold text-base hover:underline">{tweet.userName}</span>
                        {#if tweet.verified}
                            <TweetIcon icon={Icons.Verified} className="text-lg ml-1" variation='rounded'/>
                        {/if}
                        <span class="px-2 py-1 text-zinc-400/80 text-sm">@{tweet.userId} · {tweet.timeAgo}</span>
                    </header>
                    {#if tweet.summary}
                        <span class="text-sm pr-4">{@html tweet.summary}</span>
                    {/if}
                    {#if tweet.image}
                        <img src={tweet.image} alt={tweet.userName} class="rounded-2xl mr-4 mt-2">
                    {/if}
                    {#if tweet.video}
                        {#if toggleVideo}
                            <img src={tweet.video.poster} alt={tweet.userName} class="rounded-2xl mr-4 mt-2" on:click={onToggleVideo}/>
                        {:else}
                            <video preload="auto" playsinline src={tweet.video.src} alt={tweet.userName} poster={tweet.video.poster} class="rounded-2xl mr-4 mt-2" autoplay loop on:click={onToggleVideo}/>
                        {/if}
                    {/if}
                    {#if tweet.gallery?.length === 4}
                        <div class="grid grid-cols-2 grid-rows-2 mr-4 mt-2">
                            <div alt={tweet.userName} class="border border-zinc-900 outline-none w-full aspect-video rounded-tl-xl bg-center bg-cover" style="background-image:url('{tweet.gallery[0]}')"/>
                            <div alt={tweet.userName} class="border border-zinc-900 outline-none w-full aspect-video rounded-tr-xl bg-center bg-cover" style="background-image:url('{tweet.gallery[1]}')"/>
                            <div alt={tweet.userName} class="border border-zinc-900 outline-none w-full aspect-video rounded-bl-xl bg-center bg-cover" style="background-image:url('{tweet.gallery[2]}')"/>
                            <div alt={tweet.userName} class="border border-zinc-900 outline-none w-full aspect-video rounded-br-xl bg-center bg-cover" style="background-image:url('{tweet.gallery[3]}')"/>
                        </div>
                    {/if}
                    
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
                </section>
            </section>
        {/each}
    </ul>
</section>