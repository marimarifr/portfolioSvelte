<svelte:head>
  <title>Sempre trabalhando</title>
</svelte:head>

<script>
  import projects from "$lib/projects.json";
</script>

<h1> Meus projetos</h1>
    <p> Veja os meus projetos em um perfil do github</p>

    
<h1>{ projects.length} Projects</h1>
    <div class="projects">
      {#each projects as p}
          <article>
          <h2>{p.title}</h2>
          <img src={p.image} alt="" />
          <p> {p.description} </p>
          </article>
      {/each}
  </div> 
 