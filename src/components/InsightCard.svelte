<script lang="ts">
  let { title, description, step } = $props<{
    title: string;
    description: string;
    step: string;
  }>();
</script>

<div class="glass p-8 rounded-3xl relative overflow-hidden group hover:bg-white/10 transition-colors duration-500 h-full flex flex-col gap-6">
  <div class="absolute -right-4 -top-4 text-[120px] font-black text-white/5 group-hover:text-white/10 transition-colors duration-500 pointer-events-none select-none">
    {step}
  </div>
  
  <h3 class="text-2xl md:text-3xl font-bold text-white leading-tight relative z-10">{title}</h3>
  
  <p class="text-lg text-foreground/80 leading-relaxed flex-grow relative z-10">
    {description}
  </p>
</div>
