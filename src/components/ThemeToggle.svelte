<script>
    import { onMount } from 'svelte';

    let isDark;

    function updateState() {
        isDark = document.documentElement.classList.contains('dark');
    }

    function toggleTheme() {
        document.documentElement.classList.toggle('dark');
        
        const currentTheme = document.documentElement.classList.contains('dark') ? 'dark' : 'light';
        localStorage.setItem('theme', currentTheme ? "dark" : "light");

        updateState();
    }

    onMount(() => {
        updateState();
    });
</script>

<button
    on:click={ toggleTheme } 
    class="aria-label='Toggle theme' p-2 rounded-lg transition relative flex items-center rounded-full p-1 transition-colors duration-300">

    {#if isDark}
        ☀️
    {:else}
        🌙
    {/if}
</button>