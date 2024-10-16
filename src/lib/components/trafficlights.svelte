<script lang="ts">
    import { gsap } from "gsap";
    import { onMount } from "svelte";

    export let circleCount = 5;
    export let baseSize = "w-24 md:w-36";
    export let colors = [
        "neutral-300",
        "neutral-400",
        "neutral-500",
        "neutral-600",
        "neutral-700",
    ];

    let circles: HTMLDivElement[] = [];

    onMount(() => {
        const timeline = gsap.timeline({ repeat: -1, yoyo: true });

        circles.forEach((circle, index) => {
            timeline.fromTo(
                circle,
                {
                    x: "-10%",
                    duration: 1,
                    ease: "power1.inOut",
                },
                {
                    x: "10%",
                    duration: 1,
                    ease: "power1.inOut",
                },
                index * 0.2,
            );
        });
    });
</script>

<div class="relative {baseSize} aspect-square">
    {#each Array(circleCount) as _, i}
        <div
            class="absolute border rounded-full aspect-square flex items-center justify-center"
            class:border-neutral-300={colors[i] === "neutral-300"}
            class:border-neutral-400={colors[i] === "neutral-400"}
            class:border-neutral-500={colors[i] === "neutral-500"}
            class:border-neutral-600={colors[i] === "neutral-600"}
            class:border-neutral-700={colors[i] === "neutral-700"}
            style="width: {100 - i * 15}%; left: {i * 7.5}%; top: {i * 7.5}%;"
            bind:this={circles[i]}
        ></div>
    {/each}
</div>
