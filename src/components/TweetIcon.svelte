<script context="module">
    export const Icons = {
      Emtpy: 'e835',
      AutoAwesome: 'e65f',
      Image: 'e3f4',
      GifBox: 'e7a3',
      Leaderboard: 'f20c',
      Mood: 'e7f2',
      EditCalendar: 'e742',
      AddLocation: 'e567',
      MoreHorizontal: 'e5d3',
      ChatBubble: 'e0ca',
      Repeat: 'e040',
      Favorite: 'e87d',
      FileUpload: 'e2c6',
      Verified: 'ef76',
    }
</script>

<script>
    export let icon = Icons.Emtpy
    export let className = ''
    export let variation = 'outlined'
</script>

<span class="material-symbols-{variation} {className}">{@html `&#x${icon}`}</span>