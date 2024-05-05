<script lang="ts">
    import { games } from '$lib/defs/games'
    import FaShoppingCart from 'svelte-icons/fa/FaShoppingCart.svelte'
    const game = window.location.pathname.split('/')[2]
    //find game by id
    const gameData = games.find(g => g.id === game)
    console.log(gameData)
    if (!gameData) window.location.replace('/shop')
    console.log(gameData.shop)
</script>
<div class="mt-20">
    {#if !gameData?.shop || gameData?.shop?.length == 0}
    <h1 class="text-4xl font-bold">No shop for this game</h1>
    {:else}
    <div class=" text-center">
        <h1 class="text-5xl font-bold">{gameData?.name}</h1>
        <h1 class="text-2xl">{gameData?.server}</h1>
    </div>
    <h1 class="text-xl font-bold">Shop:</h1>
    <div class="grid grid-cols-2 gap-4 mt-10">
        {#each gameData.shop as item}
        <div class="flex flex-col border-2 border-white rounded-xl p-3 bg-gray-800">
            <h1 class="text-2xl font-bold text-center">{item.name}</h1>
            <h1 class="text-lg">${item.price}</h1>
            <div class="flex m-auto justify-between gap-6 ">
                <button class="flex bg-blue-500 rounded-2xl  text-white py-2 px-4"><div class="icon">
                    <FaShoppingCart />
                  </div></button>
                <button class="bg-blue-500 rounded-2xl text-white py-2 px-4">buy</button>
            </div>
        </div>
        {/each}
    </div>
    {/if}
</div>