<script context="module">
  import requests from "../data/requests.js";

  export async function preload() {
    try {
      const usStats = await requests.usStats();
      const historicStats = await requests.historicUS();

      return { usStats, historicStats };
    } catch (e) {
      console.log(e);
    }
  }
</script>

<script>
  import CovidStat from "../components/CovidStat.svelte";

  import CovidChart from "../components/CovidChart.svelte";

  import TableContainer from "../components/TableContainer.svelte";

  export let usStats;
  export let historicStats;
  console.log(historicStats);
</script>

<svelte:head>
  <title>Covid 19 US Tracker</title>
</svelte:head>

<div class="section header">
  <div class="container">
    <h1>Covid 19 - US</h1>
  </div>
</div>

<CovidStat {...usStats} />

<CovidChart />

<TableContainer />
