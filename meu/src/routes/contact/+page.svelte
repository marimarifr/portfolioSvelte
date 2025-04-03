<svelte:head>
  <title>Não ligue</title>
</svelte:head>

<h1> Contatos</h1>
<p>Entre em contato comigo por email</p>

<!-- Navigation menu: -->

<h1> Preencha</h1>
<form action="mailto:mariana.rocha@fgv.edu.br" method = "GET"> 
    <!-- <label for="email">Email:</label><br> -->
    <label for="email">Email: <input id = "email" type = "email" name = "text_email"></label>
    
    <label for="subject">Assunto: <input id="subject" type="text" name="text_subject"> </label>
    <label for="body">Texto: <textarea id="body" name="text_message"></textarea> </label>

    <input type="submit" value="Submit" id="button">
    <!-- <button>Submit</button> -->
</form>