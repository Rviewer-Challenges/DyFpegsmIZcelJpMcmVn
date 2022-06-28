<script>
    import TweetSearchInput from '../components/TweetSearchInput.svelte'
    import TweetBox from '../components/TweetBox/TweetBox.svelte'
    import topics from '../mocks/topics.json'

    export let className = ''

    const boxData = topics
</script>

<section class="border-l border-zinc-600 relative {className}">
    <section class="w-[350px] sticky top-0 left-0 mx-8 py-2 hidden lg:block">
      <TweetSearchInput/>
      <TweetBox boxData={boxData}/>
    </section>
</section>