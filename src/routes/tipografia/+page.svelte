<script lang="ts">
  import Text from "$lib/components/Text/Text.svelte";
  import Markdown from "$lib/components/Markdown/Markdown.svelte";
  import Form from "$lib/components/Form/Form.svelte";
  import { tipografia } from "$lib";

  let valueInput: string;

  function handleInputValueChange(value: string) {
    valueInput = value;
  }
</script>

<svelte:head>
  <title>Voltere - Tipografia</title>
</svelte:head>

<Text classe="title" label="Tipografia" />

<Form router="tipografia" onInputValueChange={handleInputValueChange}>
  {#if valueInput}
    <p>
      {(tipografia.match(new RegExp(valueInput, "gi")) || []).length} ocorrências
      encontradas.
    </p>
  {/if}
</Form>

<Markdown label={tipografia} />
