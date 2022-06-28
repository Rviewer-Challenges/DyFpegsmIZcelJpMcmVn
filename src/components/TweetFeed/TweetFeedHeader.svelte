<script>
    import { Icons } from '../TweetIcon.svelte'
    import TweetIconButton from '../TweetIconButton.svelte'
    import TweetAvatar from '../TweetAvatar.svelte'

    export let className = ''

    const avatarSrc = 'https://pbs.twimg.com/profile_images/1470275753895997445/4te7URwk_400x400.jpg'
</script>
  
<header class="sticky h-12 left-0 top-0 flex w-full backdrop-blur-lg bg-zinc-900/75 p-1 z-10 cursor-pointer">
    <TweetAvatar src={avatarSrc} className="shrink mx-4 mt-1 sm:hidden" size='sm'/>
    <span class="shrink font-bold text-lg p-2 align-middle">
    Inicio
    </span>
    <div class="grow">
    <TweetIconButton icon={Icons.AutoAwesome} className="hover:bg-zinc-400/25 rotate-180 float-right"/>
    </div>
</header>