<script>
    export let linkImage = {
      src: '',
      href: '',
      site: '',
      title: '',
    }
</script>

<a class="flex flex-col" href={linkImage.href} target="_blank">
    <div class="border border-zinc-800 outline-none w-full aspect-video rounded-t-xl bg-center bg-cover" style="background-image:url('{linkImage.src}')"/>
    <div class="border shrink-0 border-zinc-800 outline-none w-full h-15 rounded-b-xl flex flex-col p-4 pt-2 text-sm">
    <span class="text-zinc-500">{linkImage.site}</span>
    <span>{linkImage.title}</span>
    </div>
</a>