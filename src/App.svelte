<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Navigation from "./components/Navigation.svelte";
  import IdeasList from "./components/IdeasList.svelte";
  import NewIdea from "./components/NewIdea.svelte";

  // Navigation
  let navigationTabs = ["List of Ideas", "Add New Idea", "More..."];
  let activeItem = "Add New Idea";

  const changeTab = (e) => {
    activeItem = e.detail;
  };
</script>

<Header />
<Navigation {activeItem} {navigationTabs} on:changeTab={changeTab} />
{#if activeItem === "List of Ideas"}
  <IdeasList />
{:else if activeItem === "Add New Idea"}
  <NewIdea />
{/if}
<Footer />

<style>
</style>
