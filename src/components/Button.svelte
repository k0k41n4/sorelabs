<script>
  export let href = "#";
  export let variant = "primary"; // primary, secondary
</script>

<a
  {href}
  class="inline-flex items-center justify-center px-8 py-4 text-lg font-bold transition-all duration-300 rounded-lg group
  {variant === 'primary' 
    ? 'bg-accent text-background hover:bg-accent-hover hover:scale-105 shadow-[0_0_20px_rgba(255,140,0,0.3)] hover:shadow-[0_0_30px_rgba(255,140,0,0.5)]' 
    : 'border-2 border-accent text-accent hover:bg-accent hover:text-background'}"
>
  <slot />
  {#if variant === "primary"}
    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 ml-2 transition-transform group-hover:translate-x-1" viewBox="0 0 20 20" fill="currentColor">
      <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
    </svg>
  {/if}
</a>
