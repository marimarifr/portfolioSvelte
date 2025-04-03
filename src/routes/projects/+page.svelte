<script>
  import projects from "$lib/projects.json";
  import Project from "$lib/Project.svelte";
  import Pie from '$lib/Pie.svelte';
  import * as d3 from 'd3';

  
  $: filteredProjects = projects.filter(project => {
    let values = Object.values(project).join("\n").toLowerCase();
    return values.includes(query.toLowerCase());
  });

  let query = "";
  
  let pieData;

  $: {
      pieData = {};
      let rolledData = d3.rollups(filteredProjects, v => v.length, d => d.year);
      pieData = rolledData.map(([year, count]) => {
          return { value: count, label: year };
      });
}

$: filteredByYear = filteredProjects.filter(project => {
        if (selectedYear) {
            return project.year === selectedYear;
        }

        return true;
    });


  let selectedYearIndex = -1;
  let selectedYear;
  $: selectedYear = selectedYearIndex > -1 ? pieData[selectedYearIndex].label : null;

  
</script>

<svelte:head>
<title>Projects</title>
</svelte:head>

<!-- <Pie data={pieData}/> -->
<Pie data={pieData} bind:selectedIndex={selectedYearIndex} />

<input type="search" bind:value={query} aria-label="Search projects" placeholder="🔍 Search projects..." />


<h1>{ filteredByYear.length } Projects</h1>
<div class="projects">
  {#each filteredByYear as p}
      <Project data={p}/>
    <!-- <article>
      <h2>{p.title}</h2>
      <img src={p.image} alt="" />
      <p>
          {p.description}
      </p>
    </article> -->
  {/each}
</div>