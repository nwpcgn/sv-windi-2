<script>
  export let visible = false;
  import { close } from "./icons";
  import { Sidepanel, Button, Icon } from "./";
</script>

<Sidepanel right bind:visible>
  
  <div class="logo" style="padding-left: 1rem;">Help</div>
  <p class="p-2">
    <Button fullWidth raised
      color="accent"
      on:click={() => {
        visible = false;
      }}
    >
      
      <span class="mr-auto">
        Close
      </span>
      <Icon path={close} />
    </Button>
  </p>
  <p>
    <i style="padding: 12px;">Blank</i>
  </p>
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
