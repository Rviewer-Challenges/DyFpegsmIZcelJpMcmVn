<script>
    import TweetAvatar from './TweetAvatar.svelte'
    import TweetIcon, { Icons } from './TweetIcon.svelte'
    import TweetButton from './TweetButton.svelte'
    import TweetIconButton from './TweetIconButton.svelte'

    export let className = ''

    const avatarSrc = 'https://pbs.twimg.com/profile_images/1470275753895997445/4te7URwk_400x400.jpg'

    // Binds
    let tweetContent = ''
    let isTweetActive = false
    let isTweetFocused = false
    const tweetRows = 1

    // Events

    function onTweetInput(e) {
      if (e && e.target) {
        const $tweetInput = e.target

        $tweetInput.style.height = 'auto'
        $tweetInput.style.height = `${$tweetInput.scrollHeight}px`
      }
    }

    function onTweetFocus(e) {
      isTweetFocused = true
    }

    function onTweetKeyUp() {
  // Tweet active/unactive on content update

      if (tweetContent.length === 0) {
        isTweetActive = false
        return
      }
      isTweetActive = true
    }
</script>

<section class="px-4 py-2 border-b border-zinc-700 {className}">
    <header class="h-8 my-4 flex justify-between">
        <span class="font-bold text-lg">Inicio</span>
        <TweetIconButton icon={Icons.AutoAwesome} className="hover:bg-zinc-900"/>
    </header>
    <section class="flex justify-between my-2" >
        <TweetAvatar src={avatarSrc} className="mr-5"/>
        <section class="grow">
            <div class="border w-24 mb-2 border-sky-100/50 text-sky-500 rounded-3xl text-xs font-bold text-center cursor-pointer hover:bg-sky-900/25 {isTweetFocused ? 'visible' : 'hidden'}">
                <span>Público</span>
                <TweetIcon icon={Icons.ExpandMore} className="align-middle"/>
            </div>
            <textarea rows={tweetRows} class="bg-black outline-none w-full resize-none peer text-xl h-10 pt-2 overflow-hidden" placeholder="¿Qué está pasando?" on:keyup={onTweetKeyUp} on:input={onTweetInput} on:focus={onTweetFocus} bind:value={tweetContent}/>
        </section>
    </section>
    <section class="flex justify-between">
        <section class="pl-16 pt-2">
            <TweetIconButton icon={Icons.Image} className="text-sky-500 hover:bg-sky-900/25"/>
            <TweetIconButton icon={Icons.GifBox} className="text-sky-500 hover:bg-sky-900/25"/>
            <TweetIconButton icon={Icons.Leaderboard} className="text-sky-500 hover:bg-sky-900/25"/>
            <TweetIconButton icon={Icons.Mood} className="text-sky-500 hover:bg-sky-900/25"/>
            <TweetIconButton icon={Icons.EditCalendar} className="text-sky-500 hover:bg-sky-900/25"/>
            <TweetIconButton icon={Icons.AddLocation} className="text-sky-500/50 hover:bg-sky-900/25" disabled={true}/>
        </section>
        <TweetButton value="Twittear" className="justify-end h-10 {!isTweetActive ? 'opacity-50 cursor-default' : ''}"/>
    </section>
</section>