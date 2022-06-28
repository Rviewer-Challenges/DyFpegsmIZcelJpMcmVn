<script>
    import TweetButton from '../TweetButton.svelte'

    export let navigationItem = {
      label: '', type: '', icon: '',
    }
</script>

<TweetButton className="w-56 h-12 hidden xl:inline" value={navigationItem.label}/>
<button class="hover:bg-sky-400 bg-sky-500 w-12 aspect-square p-2 ml-3 rounded-full self-center absolute bottom-20 right-5 sm:static sm:inline xl:hidden">
    <img src={navigationItem.icon} alt={navigationItem.label} class="w-7 grayscale invert">
</button>