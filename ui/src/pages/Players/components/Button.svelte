<script>
	import { PLAYER_VEHICLES, SELECTED_PLAYER } from '@store/players'
	import { MENU_WIDE } from '@store/stores'

	export let player

	async function SelectPlayer(player) {
		SELECTED_PLAYER.set(player)
		MENU_WIDE.set(true)
		PLAYER_VEHICLES.set(player.vehicles);
	}
</script>

<button
	class="h-[4.5vh] w-full flex items-center px-[1.5vh] rounded-[0.5vh] bg-tertiary bg-opacity-92 hover:bg-opacity-90"
	on:click={() => {
		SelectPlayer(player)
	}}
>
	<div class="w-full flex items-center justify-between gap-[1vh]">
		<p>{player.id} - {player.name}</p>
		<i class="fas fa-angle-right" />
	</div>
</button>
