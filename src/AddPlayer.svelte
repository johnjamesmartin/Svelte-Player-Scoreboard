<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let player = {
    name: "",
    points: 0
  };

  const onSubmit = e => {
    e.preventDefault();
    dispatch("addplayer", player);
    player = {
      name: "",
      points: 0
    };
  };
</script>

<form on:submit={onSubmit} class="grid-3">
  <input type="text" placeholder="Player name" bind:value={player.name} />
  <input type="number" placeholder="Player points" bind:value={player.points} />
  <input class="btn btn-primary" type="submit" placeholder="Add player" />
</form>
