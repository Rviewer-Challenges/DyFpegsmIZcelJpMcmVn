<script>
    export let className = ''
    export let avatar = {
      src: '',
    }
</script>

<span class="{className}">
    <button alt="avatar" class="w-12 h-12 rounded-full bg-[url('{avatar.src}')] bg-cover bg-no-repeat bg-left-top hover:opacity-90"/>
</span>