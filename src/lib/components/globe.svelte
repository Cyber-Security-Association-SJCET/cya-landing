<script lang="ts">
    import createGlobe from "cobe";
    import { onMount } from "svelte";

    let canvas: HTMLCanvasElement;
    let phi = 0;
    let globe: ReturnType<typeof createGlobe>;

    onMount(() => {
        if (canvas) {
            globe = createGlobe(canvas, {
                width: canvas.width,
                height: canvas.height,
                phi: 0,
                theta: 0,
                mapSamples: 10000,
                dark: 1,
                diffuse: 1.5,
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
                scale: 2,
            });

            const observer = new IntersectionObserver(
                (entries) => {
                    entries.forEach((entry) => {
                        if (entry.isIntersecting) {
                            globe.toggle(true);
                            console.log("start rendering");
                        } else {
                            globe.toggle(false);
                            console.log("stop rendering");
                        }
                    });
                },
                { threshold: 0.1 }, // Trigger when 10% of the element is visible
            );

            observer.observe(canvas);

            return () => {
                observer.disconnect();
                globe.destroy();
            };
        }
    });
</script>

<canvas bind:this={canvas} class="w-full h-full"></canvas>
