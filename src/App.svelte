<script>
  import LeftPane from './views/LeftPane.svelte'
  import TweetFeed from './views/TweetFeed.svelte'
  import RightPane from './views/RightPane.svelte'
</script>

<main class="flex flex-row lg:-ml-[300px] xl:-ml-32">
  <LeftPane className='shrink xl:grow w-full'/>
  <TweetFeed className="shrink sm:shrink-0 xs:w-full sm:w-[600px]"/>
  <RightPane className="grow w-full"/>
</main>

<style>
  :root {
    font-family: TwitterChirp, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    background-color: black;
    color: white;
    box-sizing: border-box;
  }
  *, *:before, *:after {
    box-sizing: inherit;
  }
</style>
