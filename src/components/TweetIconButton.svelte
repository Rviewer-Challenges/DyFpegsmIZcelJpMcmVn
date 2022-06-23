<script>
    import TweetIcon, { Icons } from './TweetIcon.svelte'
    
    export let icon = Icons.Emtpy
    export let className = ''
    export let iconClassName = ''
    export let size = 'lg'
    const sizeClass = size === 'sm' ? 'w-8 h-8' : 'w-10 h-10'
</script>

<button class="rounded-full pt-1 {sizeClass} {className}">
    <TweetIcon icon={icon} className={iconClassName}/>
</button>