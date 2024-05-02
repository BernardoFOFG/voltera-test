<script lang="ts">
  import { markdown } from "$lib";
  import Form from "$lib/components/Form/Form.svelte";
  import Markdown from "$lib/components/Markdown/Markdown.svelte";
  import Text from "$lib/components/Text/Text.svelte";

  let valueInput: string;

  function handleInputValueChange(value: string) {
    valueInput = value;
  }
</script>

<svelte:head>
  <title>Voltere - Markdown</title>
</svelte:head>

<Text classe="title" label="markdown" />

<Form router="markdown" onInputValueChange={handleInputValueChange}>
  {#if valueInput}
    <p>
      {(markdown.match(new RegExp(valueInput, "gi")) || []).length} ocorrências encontradas.
    </p>
  {/if}
</Form>

<Markdown label={markdown} />
