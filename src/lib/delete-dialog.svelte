<script lang="ts">
	import * as AlertDialog from '$lib/components/ui/alert-dialog';
	import { Button } from '$lib/components/ui/button';
	import { createEventDispatcher } from 'svelte';
  import { itemIsSelected } from './store';

	export let open = false;

</script>

<!-- Alert Dialog for deleting a menu item -->
<AlertDialog.Root bind:open>
	<AlertDialog.Content>
		<AlertDialog.Header>
			<AlertDialog.Title>
				Are you sure you want to delete this item?
			</AlertDialog.Title>
			<AlertDialog.Description>
				This action cannot be undone. This will permanently delete the item from or servers.
			</AlertDialog.Description>
		</AlertDialog.Header>
		<AlertDialog.Footer>
			<AlertDialog.Cancel>Cancel</AlertDialog.Cancel>
				<Button on:click={() => $itemIsSelected = false} variant="destructive">
					Delete
				</Button>
		</AlertDialog.Footer>
	</AlertDialog.Content>
</AlertDialog.Root>