<script>
  export let series;
  export let colors;
  export let selected;

  function lineExpression(points) {
    return points.map(([x, y]) => `${x} ${y}`).join("\n");
  }

  function handleClick(series, point) {
    selected = {series, point}
  }

  $: lines = series.map(lineExpression)
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
    {#each lines as expression, index}
      <polyline
         fill="none"
         stroke={colors[index]}
         stroke-width="2"
         stroke-linecap="round"
         stroke-linejoin="round"
         points={expression}/>
    {/each}

    {#each series as points, serie}
      {#each points as point}
        <circle
          class:selected={selected && point == selected.point && serie == selected.series-1}
          cx={point[0]}
          cy={point[1]}
          r=3
          fill=white
          on:click|preventDefault={() => handleClick(serie+1, point)}/>
      {/each}
    {/each}
  </svg>
</div>
