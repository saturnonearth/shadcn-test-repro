<script>
  import { Button } from "$lib/components/ui/button";
  import DeleteDialog from "$lib/delete-dialog.svelte";
  import { itemIsSelected } from "$lib/store";
  import { fly } from "svelte/transition";

  export let open = false;
</script>

<Button on:click={() => open = true}>Open Dialog</Button>
 
{#if $itemIsSelected}
  <div
    in:fly={{ x: 400, duration: 250, opacity: 1 }}
    out:fly={{ x: 400, duration: 250, opacity: 0 }}
  >
    <DeleteDialog bind:open />
  </div>
{/if}