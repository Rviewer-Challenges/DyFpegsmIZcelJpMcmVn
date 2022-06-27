<script>
    import TweetNavigation from '../components/TweetNavigation.svelte'
    
    export let className = ''
</script>

<section class="border-r border-zinc-700 pr-4 relative {className}">
    <TweetNavigation className="sticky right-0 top-0 float-right w-[60px] xl:w-[250px]"/>
</section>