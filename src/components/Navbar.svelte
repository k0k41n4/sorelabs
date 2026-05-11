<script>
  import Logo from "./Logo.svelte";
  let isMenuOpen = $state(false);

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  const navLinks = [
    { name: "Features", href: "#features" },
    { name: "Plans", href: "#pricing" },
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
        href="mailto:myslatudio@gmail.com?subject=Inquiry:%20High-Performance%20Infrastructure%20for%20[Business%20Name]&body=Hi%20Kresna,%0D%0A%0D%0AMy%20business%20is:%20[Name/URL]%0D%0AOur%20main%20goal%20with%20this%20project%20is:%20[Goal]%0D%0AOur%20target%20launch%20date%20is:%20[Date]%0D%0A%0D%0AI%20confirm%20that%20we%20are%20ready%20to%20invest%20in%20the%20$3,000+%20premium%20standard.%0D%0A%0D%0ALet%27s%20build%20something%20fast." 
        target="_blank"
        rel="noopener noreferrer"
        class="px-6 py-3 bg-accent text-background text-sm font-black rounded-xl hover:bg-accent-hover transition-all tracking-widest uppercase"
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
          href="mailto:myslatudio@gmail.com?subject=Inquiry:%20High-Performance%20Infrastructure%20for%20[Business%20Name]&body=Hi%20Kresna,%0D%0A%0D%0AMy%20business%20is:%20[Name/URL]%0D%0AOur%20main%20goal%20with%20this%20project%20is:%20[Goal]%0D%0AOur%20target%20launch%20date%20is:%20[Date]%0D%0A%0D%0AI%20confirm%20that%20we%20are%20ready%20to%20invest%20in%20the%20$3,000+%20premium%20standard.%0D%0A%0D%0ALet%27s%20build%20something%20fast." 
          target="_blank"
          rel="noopener noreferrer"
          class="w-full py-5 bg-accent text-background text-center font-black rounded-2xl tracking-widest uppercase"
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
