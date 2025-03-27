<svelte:head>
  <title>Não ligue</title>
</svelte:head>

<h1> Contatos</h1>
<p>Entre em contato comigo por email</p>

<!-- Navigation menu: -->

<h1> Preencha</h1>
<form action="mailto:mariana.rocha@fgv.edu.br" method = "get"> 
    <!-- <label for="email">Email:</label><br> -->
    <label for="email">Email:</label><br>
    <input name = "email" type = "email"><br>
    <label for="subject">Assunto:</label><br>
    <input name = "subject"><br>
    <label for="body">Texto:</label><br>
    <textarea name = "body"></textarea>
    <button>Submit</button>
</form>