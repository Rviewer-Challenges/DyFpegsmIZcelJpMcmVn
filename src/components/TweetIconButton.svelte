<script>
    import TweetIcon, { Icons } from './TweetIcon.svelte'
    
    export let icon = Icons.Emtpy
    export let className = ''
    export let iconClassName = ''
</script>

<button class="rounded-full w-10 h-10 pt-1 {className}">
    <TweetIcon icon={icon} className={iconClassName}/>
</button>