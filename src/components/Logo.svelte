<script>
  export let size = "md";
  
  const sizes = {
    sm: "text-2xl",
    md: "text-4xl",
    lg: "text-6xl"
  };
</script>

<div class="flex items-center gap-1 font-bold tracking-tighter {sizes[size]}">
  <span>S</span>
  <div class="relative flex items-center justify-center w-[1.1em] h-[1.1em]">
    <!-- Sun Icon for 'O' -->
    <svg viewBox="0 0 24 24" class="w-full h-full text-accent animate-spin-slow">
      <!-- 12 Thin Rays -->
      {#each Array(12) as _, i}
        <rect
          x="11.6"
          y="1"
          width="0.8"
          height="4.5"
          rx="0.4"
          fill="currentColor"
          style="transform-origin: 12px 12px; transform: rotate({i * 30}deg);"
        />
      {/each}
      <!-- Sun Core -->
      <circle cx="12" cy="12" r="4.8" fill="currentColor" />
      <!-- Subtle Inner Ring -->
      <circle cx="12" cy="12" r="3" fill="none" stroke="black" stroke-opacity="0.2" stroke-width="0.5" />
    </svg>
  </div>
  <span>RELABS</span>
</div>

<style>
  @keyframes spin-slow {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
  .animate-spin-slow {
    animation: spin-slow 20s linear infinite;
  }
</style>
