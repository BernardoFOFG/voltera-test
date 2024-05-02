<script lang="ts">
  export let classe: "title" | "subtitle";
  export let label: string;
</script>

{#if classe === "title"}
  <h1 class={classe}>{label}</h1>
{/if}

<style>
  .title {
    color: var(--green-md);

    text-transform: capitalize;
    margin-bottom: 24px;
  }
</style>
