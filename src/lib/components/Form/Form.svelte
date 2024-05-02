<script lang="ts">
  import { onMount } from "svelte";

  export let router: string;
  export let onInputValueChange: any;

  let campoValor = "";

  function handleSubmit(event: Event) {
    event.preventDefault();
    const queryString = `?q=${encodeURIComponent(campoValor)}`;
    window.location.href = `${router}${queryString}`;
  }

  onMount(() => {
    const urlParams = new URLSearchParams(window.location.search);
    campoValor = urlParams.get("q") || "";
    onInputValueChange(campoValor);
  });

  function handleInputChange() {
    onInputValueChange(campoValor);
  }
</script>

<div class="box-search">
  <form on:submit={handleSubmit}>
    <input
      type="text"
      id="campo"
      bind:value={campoValor}
      on:input={handleInputChange}
      required
    />
    <button type="submit">Enviar</button>
    <slot />
  </form>
</div>

<style>
  .box-search {
    display: flex;
    align-items: center;
    gap: 16px;
    color: #fff;
    margin-bottom: 16px;
  }

  .box-search input {
    padding: 1rem;
    background-color: var(--dark-black);
    border: none;
    width: 20rem;
    border-radius: 0.25rem;
    color: #fff;
  }

  .box-search button {
    padding: 1rem;
    border: none;
    border-radius: 0.25rem;
    background-color: var(--green-dark);
    color: #fff;
  }

  .box-search button:hover {
    opacity: 0.7;
    cursor: pointer;
  }

  @media only screen and (max-width: 768px) {
    .box-search,
    .box-search input {
      width: 100%;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
      width: 100%;
    }
  }
</style>
