<script>
  import projects from "$lib/projects.json";
  import Project from "$lib/Project.svelte";
  import Pie from '$lib/Pie.svelte';
</script>

<svelte:head>
  <title>Projects</title>
</svelte:head>

<h1>{ projects.length } Projects</h1>
<Pie />
<div class="projects">
  {#each projects as p}
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