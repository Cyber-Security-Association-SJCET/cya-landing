<script lang="ts">
    import { gsap } from "gsap";
    import { onMount } from "svelte";

    let square1: HTMLDivElement;
    let square2: HTMLDivElement;
    let square3: HTMLDivElement;
    let square4: HTMLDivElement;
    let square5: HTMLDivElement;

    onMount(() => {
        const squares = [square1, square2, square3, square4, square5];
        const timeline = gsap.timeline({ repeat: -1, yoyo: true });

        squares.forEach((square, index) => {
            timeline.fromTo(
                square,
                {
                    rotation: -10,
                    duration: 1,
                    ease: "power1.inOut", 
                },
                {
                    rotation: 10,
                    duration: 1,
                    ease: "power1.inOut",
                },
                index * 0.5,
            );
        });
    });
</script>

<div
    class="border border-neutral-300 rounded-xl w-28 md:w-36 aspect-square flex items-center justify-center"
    bind:this={square1}
>
    <div
        class="border border-neutral-400 rounded-xl w-24 md:w-28 aspect-square flex items-center justify-center"
        bind:this={square2}
    >
        <div
            class="border border-neutral-500 rounded-xl w-20 md:w-20 aspect-square flex items-center justify-center"
            bind:this={square3}
        >
            <div
                class="border border-neutral-600 rounded-xl w-16 md:w-14 aspect-square flex items-center justify-center"
                bind:this={square4}
            >
                <div
                    class="border border-neutral-600 rounded-xl w-12 md:w-10 aspect-square flex items-center justify-center"
                    bind:this={square5}
                ></div>
            </div>
        </div>
    </div>
</div>
