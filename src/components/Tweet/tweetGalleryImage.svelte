<script>
    export let src = ''
    export let className = ''
    export let square = false
</script>

<div class="border border-zinc-900 outline-none w-full {square ? 'aspect-square' : 'aspect-video'} bg-center bg-cover relative {className}" style="background-image:url('{src}')">
    <span class="bg-zinc-900 w-8 text-sm text-white font-semibold rounded absolute bottom-3 left-3 text-center">ALT</span>
</div>