<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

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

  const addPlayer = e => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };

  const removePlayer = e => {
    players = players.filter(player => player.name !== e.detail);
  };
</script>

<Navbar />
<div class="container">
  <AddPlayer on:addplayer={addPlayer} />
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as player}
      <Player
        name={player.name}
        points={player.points}
        on:removeplayer={removePlayer} />
    {/each}
  {/if}
</div>
