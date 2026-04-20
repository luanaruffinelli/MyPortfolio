<script>
  import ThemeToggle from "./ThemeToggle.svelte";
  
  let { pathname } = $props();

  let menuOpen = $state(false);

  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  function closeMenu() {
    menuOpen = false;
  }
</script>

<nav class="relative w-full flex justify-center mt-4 px-2">
  
  <div class="w-full max-w-6xl bg-white/70 dark:bg-gray-800/70 backdrop-blur-md shadow-md rounded-2xl px-6 py-4 flex items-center justify-between transition">

    <!--logo-->
    <div class="text-xl font-semibold text-purple-500 gap-2">
      Luana ✦
    </div>

    <!--menú -->
    <ul class="hidden md:flex items-center gap-8 text-gray-600 dark:text-gray-300 font-medium"> 
      
      <li>
        <a href="/" class="relative transition-all duration-300 ease-in-out hover:text-purple-500 {pathname === '/' ? 'text-purple-500' : ''}">
          Inicio
          {#if pathname === '/'}
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded"></span>
          {/if}
        </a>
      </li>

      <li>
        <a href="/sobre-mi" class="relative transition-all duration-300 ease-in-out hover:text-purple-500 {pathname === '/sobre-mi' ? 'text-purple-500' : ''}">
          Sobre mí
          {#if pathname === '/sobre-mi'}
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded"></span>
          {/if}
        </a>
      </li>

      <li>
        <a href="/experiencia" class="relative transition-all duration-300 ease-in-out hover:text-purple-500 {pathname === '/experiencia' ? 'text-purple-500' : ''}">
          Experiencia
          {#if pathname === '/experiencia'}
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded"></span>
          {/if}
        </a>
      </li>

      <li>
        <a href="/contacto" class="relative transition-all duration-300 ease-in-out hover:text-purple-500 {pathname === '/contacto' ? 'text-purple-500' : ''}">
          Contacto
          {#if pathname === '/contacto'}
            <span class="absolute left-0 -bottom-1 w-full h-0.5 bg-purple-400 rounded"></span>
          {/if}
        </a>
      </li>
    </ul>

    <!--Botones-->
    <div class="flex items-center gap-4">
      
      <!--Modo oscuro-->
      <ThemeToggle />

      <!--Mobile button-->
      <button
        onclick={toggleMenu}
        class="md:hidden text-gray-600 text-2xl z-50">

        {#if menuOpen}
          ✕
        {:else}
          ☰
        {/if}

      </button>

    </div>

  </div>

  <!--Menú móvil-->
  {#if menuOpen}
    <div class="absolute top-full right-0 mt-2 md:hidden z-50">
       <div class="w-64 bg-white dark:bg-gray-800/70 shadow-2xl border border-gray-200 dark:border-gray-500 rounded-xl py-6 px-6 flex flex-col gap-5 animate-slide-in backdrop-blur-md">
        <a href="/" onclick={closeMenu} class="text-xl  text-gray-700 dark:text-gray-300 font-medium 
         hover:text-purple-500 transition">Inicio </a>
        <a href="/sobre-mi" onclick={closeMenu} class="text-xl  text-gray-700 dark:text-gray-300 font-medium 
         hover:text-purple-500 transition">Sobre mí</a>
        <a href="/experiencia" onclick={closeMenu} class="text-xl  text-gray-700 dark:text-gray-300 font-medium 
         hover:text-purple-500 transition">Experiencia</a>
        <a href="/contacto" onclick={closeMenu} class="text-xl  text-gray-700 dark:text-gray-300 font-medium 
         hover:text-purple-500 transition">Contacto</a>
      </div>
    </div>
    
  {/if}

</nav>