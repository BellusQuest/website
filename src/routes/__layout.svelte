<script lang="ts">
import Discord from "$lib/components/Discord.svelte";
import GitHub from "$lib/components/GitHub.svelte";

import { onMount } from "svelte";

  import "../app.css";

  onMount(() => {
    const loader = document.querySelector('#loader')!
    const container = document.querySelector('#animate__Me')!
    const links = document.querySelector('#links')!
    loader.classList.add('animate-out', 'fade-out', 'repeat-1', 'duration-1000')

    setTimeout(() => {
      loader.classList.add('hidden')
      container.classList.remove('hidden')
      container.classList.add('animate-in', 'fade-in', 'repeat-1', 'duration-1000')
    
      links.classList.remove('hidden')
      links.classList.add('animate-in', 'fade-in', 'duration-500', 'repeat-1')
      
    }, 500)
  });
</script>

<div id="loader" class="h-screen w-screen m-auto p-12 bg-white align-middle justify-center flex flex-row items-center">
  <img src="/bellus.min.png" class="animate__animated h-16 w-16 flex-shrink-0 animate-bounce" alt="Bellus"/>
</div>
<div id="container" class="flex flex-col gap-2 py-6 px-8 md:px-14 w-full m-auto max-w-[2168px]">
  <div id="animate__Me" class="hidden">
    <nav class="flex flex-row justify-between items-center border-b py-2 pb-4">
      <img src="/bellus.min.png" class="h-16 w-16 flex-shrink-0" alt="Bellus"/>
      <h1 class="text-5xl vibes">bellus</h1>
    </nav>
    <main class="py-3">
      <slot />
    </main>
  </div>
  <div class="py-4 md:py-0 absolute bottom-10 flex flex-row gap-4 items-center hidden" id="links">
    <a href="https://github.com/BellusQuest" alt="Discord Server" rel="external" target="_blank">
        <GitHub class="href"></GitHub>
    </a>
    <a href="https://discord.gg/4GuRCdKfSS" alt="Discord Server" rel="external" target="_blank">
        <Discord class="href"></Discord>
    </a>
  </div>
</div>
