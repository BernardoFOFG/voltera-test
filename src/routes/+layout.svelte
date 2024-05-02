<script>
  import "$lib/assets/styles/reset.css";
  import "$lib/assets/styles/global.css";
  import SidebarWeb from "$lib/components/Sidebar/SidebarWeb.svelte";
  import SidebarMobile from "$lib/components/Sidebar/SidebarMobile.svelte";
</script>

<main class="wrapper">
  <div class="sidebar-web">
    <SidebarWeb />
  </div>
  <div class="sidebar-mobile">
    <SidebarMobile />
  </div>
  <div class="container">
    <slot></slot>
  </div>
</main>

<style>
  :root {
    --main-color: #232324;
    --dark-black: #181819;
    --green-dark: #58a72d;
    --green-md: #569610;
    --green-light: #b9da31;
    --text-gradient: linear-gradient(
      to right,
      var(--green-dark),
      var(--green-md),
      var(--green-light)
    );
  }

  .wrapper {
    width: 100%;
    height: 100vh;
    background-color: var(--main-color);
    display: flex;
    overflow-y: hidden;
  }

  .container {
    width: calc(100% - 20rem);
    padding: 2rem;
  }

  .sidebar-mobile {
    display: none;
  }

  @media only screen and (max-width: 768px) {
    .container {
      width: 100%;
    }

    .wrapper {
      flex-direction: column;
      overflow-y: scroll !important;

    }

    .sidebar-web {
      display: none;
    }

    .sidebar-mobile {
      display: flex;
    }
  }
</style>
