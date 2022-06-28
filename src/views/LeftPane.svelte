<script>
    import TweetNavigation from '../components/TweetNavigation.svelte'
    
    export let className = ''
</script>

<section class="relative bg-black z-10 border-r border-zinc-700 {className}">
    <TweetNavigation className="sticky left-0 sm:right-0 top-0 sm:float-right sm:w-[70px] xl:w-[250px]"/>
</section>