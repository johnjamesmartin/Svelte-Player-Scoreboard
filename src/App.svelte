<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";

  let players = [
    {
      name: "Bennie Duncan",
      points: 42
    },
    {
      name: "Jess Wallace",
      points: 92
    },
    {
      name: "Kai Johnston",
      points: 2
    },
    {
      name: "Hayden Kelly",
      points: 55
    },
    {
      name: "Harper Butler",
      points: 137
    }
  ];
</script>

<Navbar />
<div class="container">
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as player}
      <Player name={player.name} points={player.points} />
    {/each}
  {/if}
</div>
