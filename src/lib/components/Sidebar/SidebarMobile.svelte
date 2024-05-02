<script>
  import Logo from "$lib/assets/images/logo.svg";
  import Content from "./Content.svelte";
</script>

<div class="sidebar-wrapper">
  <div class="sidebar-content">
    <a href="/">
      <img src={Logo} alt="Logo Voltera" />
    </a>

    <Content />
  </div>
</div>

<style>
  .sidebar-wrapper {
    width: 100%;
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

</style>
