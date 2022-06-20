<script>
  import LeftPane from './views/LeftPane.svelte'
  import TweetFeed from './views/TweetFeed.svelte'
  import RightPane from './views/RightPane.svelte'
</script>

<main class="grid grid-cols-3">
  <LeftPane/>
  <TweetFeed/>
  <RightPane/>
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
