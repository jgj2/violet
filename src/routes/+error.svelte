<script lang="ts">
    import {page} from '$app/state';
</script>

<h2 class="text-lg">{page.status}</h2>
<p class="text-md">{page.error?.message}</p>