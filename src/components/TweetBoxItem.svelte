<script>
    const boxItem = { topic: 'Topic', name: '#Name', tweets: 0 }
</script>


<li class="h-18 flex flex-col justify-between py-1 px-4 hover:bg-zinc-800">
    <span class="text-zinc-400 text-xs">{boxItem.topic}</span>
    <span class="text-white text-sm font-semibold">{boxItem.name}</span>
    <span class="text-zinc-400 text-xs">{`${boxItem.tweets} Tweets`}</span>
</li>