<script lang="ts">
  import Logo from "$lib/assets/images/logo.svg";
  import Content from "./Content.svelte";
</script>

<div class="sidebar-wrapper">
  <div class="sidebar-content">
    <a href="/">
      <img src={Logo} alt="Logo Voltera" />
    </a>

    <Content />

    <div class="sidebar-content__user-info">
      <p class="text-gradient">Bernardo Filipe</p>
      <p class="text-gradient">Desenvolver Front-end</p>
    </div>
  </div>
</div>

<style>
  .sidebar-wrapper {
    width: 20rem;
    height: 100vh;
    background: var(--dark-black);
    padding: 1.5rem;
  }

  .sidebar-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    height: 100%;
  }

  .sidebar-content img {
    margin-bottom: 24px;
    width: 120px;
  }

  .sidebar-content__user-info p {
    font-weight: 500;
  }

  .sidebar-content .text-gradient {
    background-image: var(--text-gradient);
    color: white;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
</style>
