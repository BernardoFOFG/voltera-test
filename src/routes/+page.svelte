<script>
  import Text from "$lib/components/Text/Text.svelte";
</script>

<Text label="Bem vindo" classe="title" />
<div class="welcome">
  <p>
    A finalidade da criação dessa página serve para atender teste prático da
    empresa <span>Voltera</span>.
  </p>

  <p>
    Nossa aplicação é simples, composta por 3 telas, cada uma com um input e um
    texto. O objetivo é digitar um texto específico e a aplicação mostrará
    quantas vezes esse texto foi repetido
  </p>

  <a href="/tipografia">Clique aqui para começar!</a>
</div>

<style>
  .welcome {
    color: #fff;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .welcome p:first-child span {
    color: var(--green-md);
    font-weight: bold;
  }

  .welcome a {
    padding: 1rem;
    background-color: var(--green-md);
    color: #fff;
    border-radius: 0.25rem;
    text-align: center;
  }

  .welcome a:hover {
    opacity: 0.7;
  }
</style>
