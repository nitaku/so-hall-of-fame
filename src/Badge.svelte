<script>
    export let d

    function formatDate(date) {
        return ''
    }
  </script>
  
  <main>
    <div>{d.player.username}</div>
    <div>{formatDate(new Date(d.session_info.timestamp_local))}</div>
  </main>
  
  <style>
  
  </style>
  