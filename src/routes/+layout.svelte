<script lang="ts">
    import "./layout.css";
    // import favicon from '$lib/assets/favicon.svg';

    let { children } = $props();

    export const prerender = true;
</script>

<svelte:head><link rel="icon" /></svelte:head>
{@render children()}
