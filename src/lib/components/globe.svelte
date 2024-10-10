<script lang="ts">
    import createGlobe from "cobe";
    import {onMount} from "svelte";

    let canvas: HTMLCanvasElement;

    let phi = 0;

    onMount(() => {
        if(canvas){
            createGlobe(canvas, {
                width: canvas.width,
                height: canvas.height,
                phi: 0,
                theta: 0,
                mapSamples: 10000,
                dark: 1,
                diffuse: 1.50,
                mapBrightness: 20,
                onRender: (state) => {
                    state.phi = phi;
                    state.width = canvas.width;
                    state.height = canvas.height;
                    phi += 0.005;
                },
                baseColor: [0.1, 0.1, 0.1],
                markerColor: [1, 1, 1],
                glowColor: [0.5, 0.5, 0.5],
                offset: [0, 450],
                markers: [],
                devicePixelRatio: 1,
                scale: 2
            })
        }
    });
</script>

<canvas bind:this={canvas} class="w-full h-full">

</canvas>