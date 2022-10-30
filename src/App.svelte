<script>
  import { onMount } from 'svelte'
  import Badge from './Badge.svelte'

  let data = []

  // when the App is ready, fetch some data
	onMount(async function () {
    data = await fetch_data()
	})

  async function fetch_data() {
    let response = await fetch('data/hall_of_fame.json')
    let text = await response.text()
    return text.split('\n').filter(row => row != '').map(row => JSON.parse(row))
  }
</script>

<main>
  {#each data as d}
    <Badge {d}/>
  {/each}
</main>

<style>

</style>
