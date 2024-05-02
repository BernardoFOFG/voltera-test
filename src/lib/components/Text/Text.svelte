<script lang="ts">
  export let classe: "title" | "subtitle";
  export let label: string;
</script>

{#if classe === "title"}
  <h1 class={classe}>{label}</h1>
{/if}

<style>
  .title {
    background-image: var(--text-gradient);
    color: white;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    

    text-transform: capitalize;
    margin-bottom: 24px;
  }
</style>
