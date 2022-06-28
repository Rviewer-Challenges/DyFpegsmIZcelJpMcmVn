<script>
  import TweetFeedHeader from '../components/TweetFeedHeader.svelte'
  import Tweet from '../components/Tweet/Tweet.svelte'
  import { Icons } from '../components/TweetIcon.svelte'
  import TweetIconButton from '../components/TweetIconButton.svelte'

  export let className = ''
  
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
      userId: 'Microsoft',
      userName: 'Microsoft',
      verified: true,
      userImage: 'https://pbs.twimg.com/profile_images/1454912483248930822/_hO4WPRC_400x400.png',
      summary: '131 governments orgs, 1 cybersecurity solution.<br/><br/>Our partnership with <span class="text-sky-500 hover:underline">@WAGovernment</span> locked down the networks and data of each individual agency with a single security program: <a href="https://msft.it/6000bo6FE" target="_blank" class="text-sky-500">msft.it/6000bo6FE</a>',
      linkImage: {
        src: 'https://pbs.twimg.com/media/FV48iwkWQAEpniW?format=jpg&name=medium',
        href: 'https://msft.it/6000bo6FE',
        site: 'microsoft.com',
        title: 'Western Australian Government continues to improve its cybersecurity',
      },
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
</script>

<section class="flex flex-col relative {className}">
    <header class="h-12 left-0 top-0 flex justify-between w-full backdrop-blur sticky bg-zinc-900/25 p-1 z-10 cursor-pointer">
        <span class="font-bold text-lg p-2">Inicio</span>
        <TweetIconButton icon={Icons.AutoAwesome} className="hover:bg-zinc-400/25 rotate-180"/>
    </header>
    <TweetFeedHeader className="shrink"/>
    <span class="h-13 text-center py-3 border-b border-zinc-700 hover:bg-zinc-900/50 cursor-pointer text-sky-400">Mostrar 7 Tweets</span>
    <ul class="grow">
        {#each tweets as tweet}
            <Tweet tweet={tweet}/>
        {/each}
    </ul>
</section>