<script>
  export let tier = "1";
  export let title = "";
  export let price = "";
  export let target = "";
  export let pitch = "";
  export let highlight = false;
</script>

<div class="flex flex-col p-8 transition-all duration-500 border-b md:border-b-0 md:border-r border-border last:border-r-0 hover:bg-white/5 group text-center md:text-left overflow-hidden">
  <div class="mb-8">
    <h3 class="mb-2 text-xl font-medium text-muted break-words">Tier {tier}: {title}</h3>
    <div class="h-px w-full bg-border group-hover:bg-accent transition-colors duration-500"></div>
  </div>

  <div class="mb-8">
    <p class="text-sm font-bold tracking-wider text-muted uppercase mb-1">Price:</p>
    <p class="text-2xl font-bold break-words {highlight ? 'text-accent' : 'text-foreground'}">{price}</p>
  </div>

  <div class="mb-8">
    <p class="text-sm font-bold tracking-wider text-muted uppercase mb-1">Target:</p>
    <p class="text-lg leading-relaxed text-foreground/80 break-words">{target}</p>
  </div>

  <div class="flex-grow">
    <p class="text-sm font-bold tracking-wider text-muted uppercase mb-1">Pitch:</p>
    <p class="text-lg leading-relaxed text-foreground/90 italic break-words">{pitch}</p>
  </div>
</div>
