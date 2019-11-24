<script>
	import Chart from './components/Chart.svelte'

  let selected = null;

  let points = [
    [ 0, 120 ],
    [ 20, 60 ],
    [ 40, 80 ],
    [ 60, 20 ],
    [ 65, 40 ]
  ]

  $: lastX = points[points.length-1][0]

  function add() {
    points.push([lastX + randomNumber(20), randomNumber(80)])
    points = points
  }

  function randomNumber(max) {
    return Math.round(Math.random() * 100) % max
  }
</script>

<main>
  <Chart {points} bind:selected/>

  <button on:click|preventDefault={add}>Add Point</button>

  {selected}
</main>
