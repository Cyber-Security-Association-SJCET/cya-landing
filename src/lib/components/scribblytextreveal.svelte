<script lang="ts">
  import { gsap } from "gsap";
  import { onMount } from "svelte";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  export let text: string;

  let paragraph: HTMLParagraphElement;

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    const chars = paragraph.innerText.split('');
    paragraph.innerHTML = '';
    chars.forEach((char) => {
      const span = document.createElement('span');
      span.textContent = char;
      span.style.opacity = '0';
      span.style.display = 'inline-block';
      paragraph.appendChild(span);
    });

    gsap.to(paragraph.children, {
      opacity: 1,
      duration: 0.5,
      stagger: {
        each: 0.05,
        from: "random"
      },
      ease: "power2.inOut",
      scrollTrigger: {
        trigger: paragraph,
        start: "top 80%",
        end: "bottom 20%",
        scrub: true,
      }
    });
  });
</script>

<p bind:this={paragraph} class="p-6 pb-0 text-neutral-300 flex-grow lg:text-justify">
   WORLD ENCRYPTION DAY
</p>