<script>
    let message = $state("Hola! Soy Lua Ruffinelli");
    let clicked = $state(false);

    function changeMessage() {
        message = "Gracias por visitar mi portfolio! ;D";
        clicked = true;
    }
</script>

<div class="bg-white/70 backdrop-blur-md border border-purple-200 rounded-xl p-4 text-center space-y-3">
    <h1 class="text-4xl md:text-5xl font-bold text-gray-800">
        {message}
    </h1>

    <p class="text-gray-600 max-w-xl mx-auto">
        Estudiante y desarrolladora en formación, creando proyectos web modernos con Astro, Svelte y Tailwind.
    </p>

    <button 
        onclick={changeMessage}
        class="bg-purple-500 hover:bg-purple-600 text-white px-6 py-3 rounded-xl shadow-md transition hover:scale-105"
    >
        {clicked ? "✔ Gracias!" : "Saludar"}
    </button>
</div>