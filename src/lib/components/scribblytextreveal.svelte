<!-- <script lang="ts">
  import { gsap } from "gsap";
  import { onMount } from "svelte";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  let paragraph: HTMLParagraphElement;

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    // Split the text into words
    const words = text.split(/\s+/);

    // Wrap each word in a span
    paragraph.innerHTML = words
      .map((word) => `<span class="word">${word} </span>`)
      .join("");

    // Set up the GSAP animation
    gsap.from(paragraph.querySelectorAll(".word"), {
      opacity: 0,
      x: xOffset,
      duration: animationDuration,
      stagger: staggerDelay,
      ease: ease,
      delay: animationDelay,
      scrollTrigger: {
        trigger: paragraph,
        start: triggerStart,
        end: triggerEnd,
        toggleActions: "play none none reverse",
      },
    });
  });
</script>

<p
  bind:this={paragraph}
  class="p-6 pb-0 text-neutral-300 flex-grow lg:text-justify"
>
  {text}
</p> -->
