<script>
    export let navigationItem = {
      label: '', type: '', icon: '',
    }
</script>

<button class="hover:bg-sky-900/25  w-12 aspect-square p-3 ml-3 rounded-full {navigationItem.mobile ? 'inline' : 'hidden sm:inline'}">
    <img src={navigationItem.icon} alt={navigationItem.label} class="w-7 grayscale invert">
</button>