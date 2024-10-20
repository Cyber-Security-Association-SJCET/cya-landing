<script lang="ts">
    import { gsap } from "gsap";
    import { onMount } from "svelte";
    import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
    import Textanimation from "./textanimation.svelte";

    export let names: string;
    export let paragraph: string;
    export let pname1: string;
    export let pname2: string;
    export let pno: string;
    export let imgsrc: string;
</script>

<!-- text-white rounded-3xl  border border-gray-300 -->
<div class="max-w-xl p-0">
    <div class="p-3 border rounded-t-3xl border-white">
        <h2 class="text-lg font-semibold">{pno}</h2>
    </div>
    <div
        class="flex flex-col p-6 justify-start border border-white"
        id="wormhole"
    >
        <h1 class="text-6xl font-bold mb-2">{pname1}</h1>
        <h1 class="text-6xl font-bold mb-4">{pname2}</h1>
        <p class="text-lg pl-1 mb-4">{names}</p>
    </div>
    <p class="p-6 border border-white text-justify">
        <Textanimation text={paragraph} />
    </p>
    <div class="relative overflow-hidden">
        <img
            src={imgsrc}
            alt="Night scene with mountains, road, and moon"
            class="w-full h-full object-fit border border-white rounded-b-3xl"
        />
    </div>
</div>

<style>
    #wormhole {
        background: no-repeat url("/wormhole.webp") center/cover;
    }
</style>