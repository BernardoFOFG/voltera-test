<script lang="ts">
  import { page } from "$app/stores";

  const links = [
    { href: "/tipografia", label: "Tipografia" },
    { href: "/markdown", label: "Markdown" },
    { href: "/america", label: "America" },
  ];
</script>

<ul class="sidebar-content__links">
  {#each links as { href, label }}
    <li>
      <a {href} class:active={$page.url.pathname === href}>{label}</a>
    </li>
  {/each}
</ul>

<style>
  .sidebar-content__links {
    display: flex;
    flex-direction: column;
    gap: 8px;
    width: 100%;
  }

  .sidebar-content__links li {
    background-color: var(--main-color);
    width: 100%;
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 4rem;
  }

  .sidebar-content__links li a {
    display: block;
    padding: 1rem;
    width: 100%;
    font-weight: bold;
    border-radius: 4rem;
    color: var(--green-md);
    text-align: center;
  }

  .sidebar-content__links li:hover {
    opacity: 0.7;
    transition: 0.5s all;
  }

  .sidebar-content__links .active {
    background-color: var(--green-md);
    background-image: none;
    color: var(--main-color);
  }

  @media only screen and (max-width: 768px) {
    .sidebar-content__links {
      flex-direction: row;
    }

    .sidebar-content__links li a {
      padding: 0.5rem;
    }
  }

  @media only screen and (max-width: 425px) {
    .sidebar-content__links {
      flex-direction: column;
      gap: 4px;
    }
  }
</style>
