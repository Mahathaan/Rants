<script lang="ts">
  import { onMount } from 'svelte';
  import { writes } from '../../data/data';
  import type { Write } from '../../data/data';

  interface EnhancedWrite extends Write {
    color: string;
  }

  let items: EnhancedWrite[] = [];

  const colors = ['#FE4806', '#FEE506', '#FC34FF', '#DDFE06'];

  function getColors(count: number): string[] {
    let result: string[] = [];
    let lastColor: string | null = null;

    for (let i = 0; i < count; i++) {
      let availableColors = colors.filter(color => color !== lastColor);
      let randomColor = availableColors[Math.floor(Math.random() * availableColors.length)];
      result.push(randomColor);
      lastColor = randomColor;
    }

    return result;
  }

  function shuffleArray(array: any[]) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];  

  }
}

onMount(() => {
  // Shuffle the writes array before processing
  shuffleArray(writes);

  const itemColors = getColors(writes.length);
  items = writes.map((item, index) => ({
    ...item,
    color: itemColors[index],
  }));
});
</script>

<main class="container mt-5 p-4">
  <div class="space-y-6 md:space-y-8 lg:space-y-10">
    {#each items as item}
      <div 
        class="rounded-lg text-center p-4 md:p-6"
        style="background-color: {item.color}"
      >
        <p class="text-black text-[16px] md:text-[24px]">
          {item.text}
        </p>
      </div>
    {/each}
  </div>
</main>
