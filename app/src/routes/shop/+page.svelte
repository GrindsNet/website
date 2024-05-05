<script lang="ts">
    import {games} from '$lib/defs/games'
</script>

<style>
    .game-name {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        opacity: 0;
        transition: opacity 0.3s ease;
        pointer-events: none;
        z-index: 1;
    }

    .image-container:hover .game-name {
        opacity: 1;
    }
    .image-container:hover img {
        opacity: 0.6;
        cursor: pointer;
    }
</style>
<h1 class="text-7xl font-bold mt-20">Shops</h1>
<div class="grid grid-cols-3 gap-20 mt-10">
    {#each games as game}
    <div class="border-2 border-white rounded-xl w-[30rem] h-full relative">
        <a href={game.url} class="image-container">
            <img class="rounded-xl " src={game.img} alt={game.name} />
            <h3 class="text-6xl game-name text-gray-300">
                {game.name}
            </h3>
        </a>
    </div>
    {/each}
</div>
