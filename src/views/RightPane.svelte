<script>
    import TweetSearchInput from '../components/TweetSearchInput.svelte'
    import TweetBox from '../components/TweetBox.svelte'

    const boxData = {
      name: 'Qué está pasando',
      items: [
        {
          topic: 'Tecnología · Tendencia', name: 'GitHub Copilot', tweets: '5.436', image: 'https://github.blog/wp-content/uploads/2022/06/Copilot.jpeg?resize=1200%2C630',
        },
        {
          topic: 'Tendencia en México', name: 'TikTok', tweets: '539 mil', image: '',
        },
        {
          topic: 'Tendencia en México', name: '#DoctorStrange', tweets: '13,8 mil', image: '',
        },
        {
          topic: 'Entretenimiento · Tendencia', name: 'One Piece', tweets: '112 mil', image: 'https://lafrikileria.com/blog/wp-content/uploads/2021/07/one-piece-logo.jpg',
        },
      ],
    }
</script>
<section class="border-l border-zinc-700 float-right w-8/12 pl-5 py-2">
    <TweetSearchInput/>
    <TweetBox boxData={boxData}/>
</section>