<script>
  export let visible = false;
  export let currentPath = "";
  export let sitenav = [];

  import { Button, Icon, Sidepanel } from "./";

  import { close, arrowForward } from "./icons";
</script>

<Sidepanel bind:visible disableScroll>
  <div class="logo">
    <Button
      icon
      color="inherit"
      on:click={() => {
        visible = false;
      }}
    >
      <Icon path={close} />
    </Button>
    <span style="margin-left:4px;">Logo</span>
  </div>

  <div style="padding: 8px 0;">
    content
  </div>
</Sidepanel>

<style>
  .logo {
    height: 48px;
    padding: 0 4px;
    display: flex;
    align-items: center;
    color: #fff;
    background: var(--bg-app-bar);
  }
</style>
