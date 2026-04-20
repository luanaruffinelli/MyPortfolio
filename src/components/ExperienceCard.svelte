<script>
    let { title, place, date, description } = $props();
</script>

<div class="relative pl-6 border-l-2 border-purple-400 hover:-translate-y-1 transition">
    <span class="absolute -left-1.75 top-2 w-3 h-3 bg-purple-500 rounded-full"></span>
    <div class="bg-white dark:bg-gray-800 shadow-md rounded-xl p-5 mb-6 hover:shadow-lg transition">
        <h3 class="font-semibold text-lg text-gray-800 dark:text-gray-200">
            {title}
        </h3>
        <p class="text-sm text-purple-500 dark:text-purple-400">
            {place} - {date}
        </p>
        <p class="text-gray-600 dark:text-gray-300 mt-2 text-sm">
            {description}
        </p>

    </div>
</div>