<script>
  import { createEventDispatcher } from "svelte";
  let dispatch = createEventDispatcher();
  export let navigationTabs;
  export let activeItem;
</script>

<nav class="nav">
  <ul>
    {#each navigationTabs as navigationTab}
      <li
        on:click={() => dispatch("changeTab", navigationTab)}
        class:active={navigationTab === activeItem}
      >
        <div>{navigationTab}</div>
      </li>
    {/each}
  </ul>
</nav>

<style>
  .nav {
    margin-bottom: 40px;
  }
  ul {
    display: flex;
    justify-content: center;
    padding: 0;
    list-style-type: none;
  }
  li {
    margin: 0 16px;
    font-size: 18px;
    color: #555;
    cursor: pointer;
  }

  .active {
    color: rgb(139, 46, 46);
  }
</style>
