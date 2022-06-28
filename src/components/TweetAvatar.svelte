<script>
    export let className = ''
    export let src = ''
    export let size = 'lg'
</script>

<button alt="avatar" class="{size === 'sm' ? 'w-8 h-8' : 'w-12 h-12'} rounded-full bg-cover bg-no-repeat bg-left-top hover:opacity-90 {className}" style="background-image: url('{src}')"/>
