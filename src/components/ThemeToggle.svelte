<script>
    import { onMount } from 'svelte';

    let isDark = $state(false);

    onMount(() => {
        const savedTheme = localStorage.getItem('theme');

        if (savedTheme) {
            isDark = savedTheme === 'dark';
        } else {
            isDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
        }

        document.documentElement.classList.toggle('dark', isDark);
    });

    function toggleTheme() {
        isDark = !isDark;
        console.log("Dark mode:", isDark);
        document.documentElement.classList.toggle('dark', isDark);
        localStorage.setItem('theme', isDark ? 'dark' : 'light');
    }
</script>

<button
    onclick={toggleTheme} 
    class="relative w-14 h-8 flex items-center bg-gray-300 dark:bg-gray-700 rounded-full p-1 transition-colors duration-300">

    <div class="w-6 h-6 bg-white dark:bg-gray-600 rounded-full shadow-md transform transition-transform duration-300"
        class:translate-x-6={isDark}
    ></div>

    <span class="absolute left-2 text-sm">🌙</span>
    <span class="absolute right-2 text-sm">☀️</span>
</button>