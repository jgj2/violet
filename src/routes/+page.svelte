<script lang="ts">
	import { onMount } from "svelte";

    let showTermInput = false;
    onMount(() => { 
        setTimeout(() => {
            showTermInput = false;
        }, 10000);
    })
</script>

<h2 class="text-3xl italic font-extralight">aut inveniam viam aut faciam</h2>
{#if showTermInput}
    <div class="absolute bottom-2 left-2 text-lg">
        >_
    </div>
{/if}