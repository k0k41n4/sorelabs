<script>
  import Logo from "./Logo.svelte";
  let isMenuOpen = $state(false);

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  const navLinks = [
    { name: "Features", href: "#features" },
    { name: "The Asset", href: "#product" },
    { name: "Proof", href: "#proof" },
  ];
</script>

<nav class="fixed top-0 left-0 w-full z-50 border-b border-white/10 bg-background/80 backdrop-blur-xl">
  <div class="max-w-7xl mx-auto px-4 h-20 flex items-center justify-between">
    <!-- Logo -->
    <a href="/" class="hover:opacity-80 transition-opacity">
      <Logo size="sm" />
    </a>

    <!-- Desktop Links -->
    <div class="hidden md:flex items-center gap-10">
      {#each navLinks as link}
        <a 
          href={link.href} 
          class="text-sm font-medium uppercase tracking-widest text-muted hover:text-accent transition-colors"
        >
          {link.name}
        </a>
      {/each}
      <a 
        href="https://wa.me/6289670202495" 
        class="px-5 py-2.5 bg-accent text-background text-sm font-bold rounded-md hover:bg-accent-hover transition-all"
      >
        LET'S TALK
      </a>
    </div>

    <!-- Mobile Menu Button -->
    <button 
      class="md:hidden text-foreground p-2"
      onclick={toggleMenu}
      aria-label="Toggle Menu"
    >
      <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        {#if isMenuOpen}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        {:else}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        {/if}
      </svg>
    </button>
  </div>

  <!-- Mobile Menu Overlay -->
  {#if isMenuOpen}
    <div class="md:hidden absolute top-20 left-0 w-full bg-background border-b border-white/10 animate-slide-down">
      <div class="flex flex-col p-6 gap-6">
        {#each navLinks as link}
          <a 
            href={link.href} 
            class="text-xl font-bold uppercase tracking-widest text-foreground hover:text-accent transition-colors"
            onclick={() => isMenuOpen = false}
          >
            {link.name}
          </a>
        {/each}
        <a 
          href="https://wa.me/6289670202495" 
          class="w-full py-4 bg-accent text-background text-center font-bold rounded-lg"
          onclick={() => isMenuOpen = false}
        >
          LET'S TALK
        </a>
      </div>
    </div>
  {/if}
</nav>

<style>
  @keyframes slideDown {
    from { opacity: 0; transform: translateY(-10px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .animate-slide-down {
    animation: slideDown 0.3s ease-out forwards;
  }
</style>
