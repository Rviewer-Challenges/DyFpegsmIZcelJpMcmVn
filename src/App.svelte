<script>
  import LeftPane from './views/LeftPane.svelte'
  import TweetFeed from './views/TweetFeed.svelte'
  import RightPane from './views/RightPane.svelte'
</script>

<main class="relative flex flex-col-reverse sm:flex-row lg:-ml-[300px] xl:-ml-32">
  <LeftPane className='sticky bottom-0 left-0 shrink sm:static sm:w-full xl:grow'/>
  <TweetFeed className="shrink sm:shrink-0 sm:w-[600px]"/>
  <RightPane className="hidden sm:block sm:grow sm:w-full"/>
</main>

<style>
  :root {
    font-family: TwitterChirp, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    background-color: black;
    color: white;
    box-sizing: border-box;
    overflow-x: hidden;
  }
  *, *:before, *:after {
    box-sizing: inherit;
  }
</style>
