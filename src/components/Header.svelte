<script>
  import IconLinks from "./IconLinks.svelte";
  import SectionsTitlesSummary from "./SectionsTitlesSummary.svelte";
  let externalLinks = [
    { icon: "/images/github.svg", url: "https://rob174.github.io/" },
    {
      icon: "/images/linkedin.svg",
      url: "https://www.linkedin.com/in/robin-moine-a00b71199/",
    },
    { icon: "/images/mail.svg", url: "mailto:robin.moine456@gmail.com" },
  ];
  let sections = [
    { id: "about", text: "About" },
    { id: "projects", text: "Projects" },
  ];
</script>

<div id="header-container">
  <div id="header-container-title">Robin Moine</div>
  <div id="sections">
    {#each sections as v}
      <SectionsTitlesSummary anchor={"#" + v.id} name={v.text} style="margin-right: 2em;"/>
    {/each}
  </div>
  <div id="socials-icons">
    {#each externalLinks as v}
      <IconLinks iconURL={v.icon} targetURL={v.url} className="icon-links"/>
    {/each}
  </div>
</div>

<style>
  #header-container {
    background: #505050;
    padding: 0.5em;
    top: 0;
    left: 0;
    font-size: 3em;
    display: flex;
    justify-content: space-between;
  }
  #header-container-title {
    align-self: flex-start;
  }
  #socials-icons {
    align-self: flex-end;
    display: flex;
  }
  #sections {
    align-self: center;
  }
</style>
