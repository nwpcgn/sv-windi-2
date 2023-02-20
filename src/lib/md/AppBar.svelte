<script>
  export let fade = false;
  export let leftPanelVisible = false;
  export let rightPanelVisible = false;
  export let loginDialogVisible = false;

  import { onMount } from "svelte";

  import { Button, Icon, Menu, Menuitem } from "./";
  import { home, menu, invertColors, moreVert } from "./icons";

  import { theme } from "./store";

  let el;
  let legacy = true;

  const darkTheme = {
    "--color": "#eee",
    "--alternate": "#000",
    "--bg-color": "#303134",
    "--primary": "#3ea6ff",
    "--accent": "#ff6fab",
    "--divider": "rgba(255,255,255,0.175)",
    "--bg-popover": "#3f3f3f",
    "--border": "#555",
    "--label": "rgba(255,255,255,0.5)",
    "--bg-input-filled": "rgba(255,255,255,0.1)",

    "--bg-app-bar": "#838383",
    "--bg-panel": "#434343",

    "--focus-color": "rgba(62, 166, 255, 0.5)", // primary with alpha
  };

  $: if (el) {
    fade
      ? (el.style.boxShadow =
          "0 1px 2px 0 rgba(0,0,0,.2), 0 2px 6px 2px rgba(0,0,0,.18)")
      : (el.style.boxShadow = "");
  }

  onMount(async () => {
    try {
      legacy = !(
        window.CSS &&
        window.CSS.supports &&
        window.CSS.supports("(--foo: red)")
      );

      let mql = window.matchMedia("(prefers-color-scheme: dark)");
      mql.matches && setTheme("dark");
    } catch (err) {} // eslint-disable-line
  });

  function setTheme(name) {
    name = name.replace(/\s/g, "").toLowerCase();

    $theme = name;
    $theme === "dark"
      ? Object.keys(darkTheme).map((key) => {
          document.documentElement.style.setProperty(key, darkTheme[key]);
        })
      : document.documentElement.removeAttribute("style");
  }
</script>

<div class="app-bar" bind:this={el}>
  <Button
    icon
    id="hamburger"
    color="inherit"
    on:click={() => {
      leftPanelVisible = true;
    }}
  >
    <Icon path={menu} />
  </Button>

  <a id="brand" href="#/">
    nwp-studio
  </a>

  <div class="title"></div>

  <Button
  icon
  id="more"
  color="inherit"
  on:click={() => {
    rightPanelVisible = true;
  }}
>
    <Icon path={moreVert} />
</Button>

</div>

<style>
  .app-bar {
    display: flex;
    align-items: center;
    height: 48px;
    color: #fff;
    background: var(--bg-app-bar);
    font-size: 18px;
    line-height: 1;
    min-width: inherit;
    padding: 0 4px 0 6px;
    position: sticky;
    left: 0;
    top: 0;
    right: 0;
    z-index: 20;
  }
  .title {
    flex: 1;
    margin-left: 0.5rem;
  }
</style>
