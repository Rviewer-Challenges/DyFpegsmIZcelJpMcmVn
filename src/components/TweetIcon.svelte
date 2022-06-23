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
    }
</script>

<script>
    export let icon = Icons.Emtpy
    export let className = ''
</script>

<span class="material-symbols-outlined {className}">{@html `&#x${icon}`}</span>