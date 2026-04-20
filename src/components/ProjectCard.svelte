<script>
    let { title, description } = $props();

    let showMore = $state(false);

    function handleClick() {
        showMore = !showMore;
    }
</script>


<div class="bg-white/70 dark:bg-gray-700/50 backdrop-blur-md border border-purple-200 dark:border-purple-900 
        rounded-xl p-4 text-center space-y-3 animate-fade-up card flex flex-col justify-between h-full">
    
    <div class="space-y-2">
        <h3 class="text-4xl md:text-5xl font-bold text-gray-800 dark:text-gray-200 animate-fade-up">
            {title}
        </h3>

        <p class="text-sm text-gray-600 dark:text-gray-300 mt-2 min-h-80 animate-fade-up">
            {#if showMore}
                🚧 Proximamente...
            {:else}
                {description}
            {/if}
        </p>
    </div>

    <button 
        onclick={handleClick}
        class="mt-4 text-purple-500 hover:underline">
        Ver más →
    </button>
</div>