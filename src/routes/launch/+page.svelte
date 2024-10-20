<script lang="ts">
    import {gsap} from "gsap";
    import {onMount} from "svelte"

    let cursor: HTMLDivElement;

    onMount(() => {
        const tl = gsap.timeline({
            repeat: -1
        })
        tl.to(cursor, {
            opacity: 0,
            duration: 0.6
        }).to(cursor, {
            opacity: 1,
            duration: 0.6
        })
    })
</script>

<main class="flex flex-col items-center justify-center h-screen gap-12">
    <img src="/cya.webp" alt="CYA logo"/>
    <div class="w-full aspect-video absolute bg-neutral-950 -z-10 blur-3xl"></div>
    <div class="p-6 border-2 border-neutral-50 rounded-xl shadow-2xl shadow-green-950 flex flex-row gap-4 items-center">
        <a href="/" class="font-bold text-7xl text-neutral-50 font-[Jersey10]">LAUNCH</a>
        <div class="w-8 h-12 bg-white" bind:this={cursor}></div>
    </div>
</main>