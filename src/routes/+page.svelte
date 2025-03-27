<svelte:head>
  <title>Conheça-me</title>
</svelte:head>

<script>
  import projects from "$lib/projects.json";
  import Project from "$lib/Project.svelte";
</script>

<h1>Mariana</h1>

    <!-- <p> (Paragraph) represents a paragraph of text.-->
    <p>um novo site inovador</p>

    <!-- <img> (Image) tag is used to display images.-->
    <img src="images/my_image.jpeg" alt="Um cachorro em um campo de tulipas roxas", height = 400>
        <!-- Example:
            <img src="images/my_image.jpeg" alt="A description of the image">
        -->
        <h2>
          Latest Projects
        </h2>
        <div class="projects">
        {#each projects.slice(0, 3) as p}
          <Project data={p} hLevel="3"/>
        {/each}
        </div>