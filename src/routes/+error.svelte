<script lang="ts">
    import { page } from '$app/stores';
    import Page from '$lib/Page.svelte';
</script>

<Page title={$page.status.toString()}>
    <h2>{$page.error?.message}.</h2> 
    <p>Try navigating to the <a href="/">homepage</a>.</p> 
</Page>
