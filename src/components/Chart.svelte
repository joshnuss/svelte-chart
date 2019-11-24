<script>
  export let points;
  export let selected;

  $: expression = points.map(([x, y]) => `${x} ${y}`).join("\n")

  function handleClick(point) {
    selected = point
  }
</script>

<style>
  .chart {
    background: #ccc;
    padding: 1em;
  }

  circle {
    cursor: pointer;
    fill: transparent;
  }

  circle:hover {
    fill: white;
    opacity: 0.8
  }

  circle.selected {
    fill: white
  }
</style>

<div class="chart">
  <svg viewBox="0 0 500 100">
    <polyline
       fill="none"
       stroke="#0074d9"
       stroke-width="2"
       stroke-linecap="round"
       stroke-linejoin="round"
       points={expression}/>

    {#each points as point}
      <circle class:selected={point == selected} cx={point[0]} cy={point[1]} r=3 fill=white on:click|preventDefault={() => handleClick(point)}/>
    {/each}
  </svg>
</div>
