<script>

  import { goto } from "$app/navigation";
 async function main() {
    const response = await fetch("https://api.mcsrvstat.us/2/grindsnet.com");
    const data = await response.json();
    console.log(data);
    return data;
 }
 async function users() {
    const response = await fetch("https://discord.com/api/guilds/1115601081238552606/widget.json");
    const data = await response.json();
    console.log(data);
    return data;
 }
</script>
<div class="mt-40 text-center items-center justify-center">
    <h1 class="text-4xl font-bold">Welcome to Grinds Network</h1>
    <h2 class="text-2xl">All your needs to be fullfilled...</h2>
</div>
{#await main() }
<div class="loading"></div>
{:then data}
    <p>currently active players: 
        {data?.players?.online}
    </p>
{:catch error}
 <p>{error}</p>
{/await}
{#await users() }
<div class="loading"></div>
{:then data}
    <p>discord members: 
        {data?.members?.length}
    </p>
{:catch error}
 <p>{error}</p>
{/await}
<button on:click={() => goto("/shop")} class="mt-40 btn btn-primary">Browse shops</button>