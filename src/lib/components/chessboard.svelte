<script lang="ts">
    import { onMount, onDestroy } from 'svelte';
   
    const size = 4; // 4x4 board
    let isWhiteStart = true;
    let board: string[][];
   
    $: board = Array(2).fill(null).map((_, row) =>
      Array(8).fill(null).map((_, col) => 
        ((row + col) % 2 === 0) === isWhiteStart ? 'bg-white' : 'bg-black'
      )
    );
   
    let interval: number;
   
    onMount(() => {
      interval = setInterval(() => {
        isWhiteStart = !isWhiteStart;
      }, 500); // Change every second
    });
   
    onDestroy(() => {
      if (interval) clearInterval(interval);
    });
   </script>
   
   <div>
    {#each board as row}
      <div class="flex">
        {#each row as cell}
          <div class="{cell} w-3 h-3"></div>
        {/each}
      </div>
    {/each}
   </div>