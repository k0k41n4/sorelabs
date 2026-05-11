<script lang="ts">
  export let name: string;
  export let price: string;
  export let features: string[];
  export let isPremium = false;
  export let billing = ""; // "/ month" or empty for one-time
</script>

<div class="relative group h-full">
  <!-- Subtle Glow on Hover -->
  <div class="absolute inset-0 bg-accent/10 blur-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500 rounded-[2.5rem] -z-10"></div>
  
  <div class="relative h-full flex flex-col p-8 md:p-10 rounded-[2.5rem] glass border border-white/5 hover:border-accent/20 transition-all duration-500 {isPremium ? 'border-accent/30 bg-accent/[0.03]' : ''}">
    {#if isPremium}
      <div class="absolute -top-4 left-1/2 -translate-x-1/2 bg-accent text-background text-[10px] font-black px-4 py-1.5 rounded-full tracking-[0.2em] uppercase shadow-[0_10px_20px_rgba(255,140,0,0.3)]">
        Recommended
      </div>
    {/if}
    
    <div class="mb-10">
      <h3 class="text-xs font-black text-accent mb-4 uppercase tracking-[0.3em]">{name}</h3>
      <div class="flex items-baseline gap-2">
        <span class="text-5xl font-extrabold text-white tracking-tighter">{price}</span>
        {#if billing}
          <span class="text-muted text-sm font-medium lowercase">{billing}</span>
        {/if}
      </div>
    </div>

    <ul class="space-y-5 mb-12 flex-grow">
      {#each features as feature}
        <li class="flex items-start gap-4 text-sm md:text-base text-foreground/70 group/item">
          <div class="mt-1 w-5 h-5 rounded-full bg-accent/10 flex items-center justify-center shrink-0 border border-accent/20 group-hover/item:bg-accent/20 transition-colors">
            <svg class="w-3 h-3 text-accent" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="3">
              <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7" />
            </svg>
          </div>
          <span class="leading-snug group-hover/item:text-foreground transition-colors">{feature}</span>
        </li>
      {/each}
    </ul>

    <a 
      href="mailto:myslatudio@gmail.com?subject=Inquiry:%20High-Performance%20Infrastructure%20for%20[Business%20Name]&body=Hi%20Kresna,%0D%0A%0D%0AMy%20business%20is:%20[Name/URL]%0D%0AOur%20main%20goal%20with%20this%20project%20is:%20[Goal]%0D%0AOur%20target%20launch%20date%20is:%20[Date]%0D%0A%0D%0AI%20confirm%20that%20we%20are%20ready%20to%20invest%20in%20the%20$3,000+%20premium%20standard.%0D%0A%0D%0ALet%27s%20build%20something%20fast."
      class="w-full py-5 text-center rounded-2xl font-black text-sm uppercase tracking-widest transition-all duration-300 {isPremium ? 'bg-white text-black hover:bg-gray-200 hover:scale-[1.02] shadow-xl' : 'bg-white/5 text-white border border-white/10 hover:bg-white/10 hover:border-white/20'}"
    >
      Connect Now
    </a>
  </div>
</div>
