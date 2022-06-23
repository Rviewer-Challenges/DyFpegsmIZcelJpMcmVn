<script>
    import TweetAvatar from './TweetAvatar.svelte'
    import { Icons } from './TweetIcon.svelte'
    import TweetButton from './TweetButton.svelte'
    import TweetIconButton from './TweetIconButton.svelte'

    const avatar = {
      src: 'https://img.freepik.com/free-photo/tennis-player-profile-picture-young-happy-man-sportswear-playing-tennis-waiting-serve_496169-1744.jpg',
    }
</script>

<section class="px-4">
    <header class="h-8 my-2 flex justify-between">
        <span class="font-bold text-lg">Inicio</span>
        <TweetIconButton icon={Icons.AutoAwesome} className="hover:bg-zinc-900"/>
    </header>
    <section class="flex justify-between my-2" >
        <TweetAvatar avatar={avatar} className="pr-5"/>
        <textarea rows="1" class="bg-black outline-none resize-none grow text-xl h-10 pt-2" placeholder="¿Qué está pasando?"/>
    </section>
    <section class="flex justify-between">
        <section class="pl-16 pt-2">
            <TweetIconButton icon={Icons.Image} className="text-sky-500 hover:bg-sky-900/25 px-2"/>
            <TweetIconButton icon={Icons.GifBox} className="text-sky-500 hover:bg-sky-900/25 px-2"/>
            <TweetIconButton icon={Icons.Leaderboard} className="text-sky-500 hover:bg-sky-900/25 px-2"/>
            <TweetIconButton icon={Icons.Mood} className="text-sky-500 hover:bg-sky-900/25 px-2"/>
            <TweetIconButton icon={Icons.AddLocation} className="text-sky-500 hover:bg-sky-900/25 px-2"/>
        </section>
        <TweetButton value="Twittear" className="justify-end"/>
    </section>
</section>