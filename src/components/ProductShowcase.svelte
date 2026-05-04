<script lang="ts">
  import { onMount } from "svelte";

  let isHovered = $state(false);
  let el: HTMLElement;
</script>

<div 
  class="relative w-full max-w-4xl mx-auto rounded-3xl p-1 bg-linear-to-b from-white/10 to-transparent overflow-hidden group"
  bind:this={el}
  onmouseenter={() => isHovered = true}
  onmouseleave={() => isHovered = false}
>
  <div class="absolute inset-0 bg-accent/20 blur-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-700 ease-out"></div>
  
  <div class="relative bg-background/90 backdrop-blur-xl border border-white/5 rounded-3xl p-8 md:p-12 flex flex-col md:flex-row gap-12 items-center justify-between z-10">
    
    <div class="flex-1 space-y-6">
      <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-accent/10 border border-accent/20 text-accent text-sm font-semibold tracking-wide">
        <span class="w-2 h-2 rounded-full bg-accent animate-pulse"></span>
        THE ULTIMATE DIGITAL ASSET
      </div>
      
      <h2 class="text-4xl md:text-5xl font-bold tracking-tight text-gradient">
        Bespoke Single-Page Funnel
      </h2>
      
      <p class="text-lg text-muted max-w-xl">
        We don't build generic websites. We engineer high-performance, conversion-optimized digital assets that act as your 24/7 top salesperson. Designed specifically for premium positioning and direct response.
      </p>

      <ul class="space-y-4 pt-4">
        {#each [
          "Bespoke UI/UX Design (No Templates)",
          "Blazing Fast Astro + Svelte Stack",
          "Advanced Micro-interactions & Animations",
          "Zero-Maintenance Serverless Setup",
          "Done-for-you Subdomain Hosting"
        ] as feature}
          <li class="flex items-center gap-3 text-foreground/80 font-medium">
            <svg class="w-5 h-5 text-accent shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7" />
            </svg>
            {feature}
          </li>
        {/each}
      </ul>
    </div>

    <div class="flex flex-col items-center justify-center p-8 bg-white/5 rounded-2xl border border-white/10 shadow-2xl relative w-full md:w-auto shrink-0 group-hover:scale-105 transition-transform duration-500">
      <div class="absolute -top-4 -right-4 bg-accent text-background text-xs font-bold px-3 py-1 rounded-full shadow-lg">
        ONLY 2 SLOTS/MONTH
      </div>
      <div class="text-muted text-sm font-medium mb-2 uppercase tracking-widest">One-Time Investment</div>
      <div class="text-5xl md:text-6xl font-extrabold text-white mb-6">
        $3,000
      </div>
      <a 
        href="https://wa.me/6289670202495"
        class="w-full text-center px-8 py-4 bg-white text-black font-bold rounded-xl hover:bg-gray-200 transition-colors shadow-[0_0_20px_rgba(255,255,255,0.3)] hover:shadow-[0_0_30px_rgba(255,255,255,0.5)]"
      >
        SECURE YOUR SLOT
      </a>
      <p class="text-xs text-muted mt-4 text-center">
        100% Custom. Delivered in 14 Days.
      </p>
    </div>

  </div>
</div>

<style>
  /* Local animations if needed, but mostly relying on Tailwind */
</style>
