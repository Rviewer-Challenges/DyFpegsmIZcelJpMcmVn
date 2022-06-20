<script>
  import LeftPane from './views/LeftPane.svelte'
  import TweetFeed from './views/TweetFeed.svelte'
  import RightPane from './views/RightPane.svelte'
</script>

<main>
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

  main {
    width: 100%;
    display: grid;
    grid-template-columns: 30% auto 30%;
  }
</style>
