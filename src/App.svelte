<script>
  import Chart from './components/Chart.svelte'

  const colors = ["teal", "salmon"]
  let selected = null;
  let series = [
    [
      [ 0, 120 ],
      [ 20, 60 ],
      [ 40, 80 ],
      [ 60, 20 ],
      [ 65, 40 ]
    ],
    [
      [ 0, 125 ],
      [ 20, 65 ],
      [ 40, 85 ],
      [ 60, 25 ],
      [ 65, 45 ]
    ]
  ]

  let lastX = 65;

  function add() {
    lastX += randomNumber(20)
    series[0].push([lastX, randomNumber(80)])
    series[1].push([lastX, randomNumber(80)])
    series = series
  }

  function randomNumber(max) {
    return Math.round(Math.random() * 100) % max
  }
</script>

<main>
  <Chart {series} {colors} bind:selected/>

  <button on:click|preventDefault={add}>Add Points</button>

  {#if selected}
    Series: {selected.series}, Point: {selected.point}
  {/if}
</main>
