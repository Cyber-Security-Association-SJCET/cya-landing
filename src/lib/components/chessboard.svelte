<script>
    const size = 4; // 4x4 board
    const board = Array(2).fill(null).map((_, row) => 
      Array(8).fill(null).map((_, col) => (row + col) % 2 === 0 ? 'bg-white' : 'bg-black')
    );
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