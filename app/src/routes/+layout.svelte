<script lang="ts">
    import "../app.css";
    import Navbar from "$lib/components/Navbar.svelte";

</script>

{#if typeof window  !== 'undefined'}
    <Navbar />
    <div class="flex flex-col items-center justify-center">
        <slot />
    </div>    
{/if}
