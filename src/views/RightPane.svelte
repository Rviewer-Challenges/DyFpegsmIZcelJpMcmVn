<script>
    import TweetSearchInput from '../components/TweetSearchInput.svelte'
    import TweetBox from '../components/TweetBox.svelte'

    const boxData = {
      name: 'Qué está pasando',
      items: [
        { topic: 'Tecnología · Tendencia', name: 'GitHub Copilot', tweets: 5436 },
        { topic: 'Tendencia en México', name: 'TikTok', tweets: 539000 },
        { topic: 'Tendencia en México', name: '#DoctorStrange', tweets: 13800 },
        { topic: 'Entretenimiento · Tendencia', name: 'One Piece', tweets: 112000 },
      ],
    }
</script>
<section class="border-l float-right w-1/2 pl-5 py-2">
    <TweetSearchInput/>
    <TweetBox boxData={boxData}/>
</section>