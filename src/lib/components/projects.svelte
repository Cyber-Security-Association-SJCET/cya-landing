<!-- <script lang="ts">
        import ProjectCard from "$lib/components/projectcard.svelte";

</script>

<div class="">
    <div class="flex overflow-x-auto gap-6 md:px-6 h-screen" >
        <ProjectCard pname1="HELIOS" pname2="BROWSER" paragraph="Helios Browser (previously known as project web) is an open source modular browser catered more towards developers, designers, and power users. It features functionalities meant to boost their workflow and automate many tasks." names="MILAN SUMAN,GAUTHAM SREERAM" pno="Project 1" imgsrc="/helios.jpg"/>
        <ProjectCard pname1="DIAFA" pname2="SPACEAPP" paragraph="This a philanthropic project created for a hackathon. This projects connects restaurants and NGOs around the world to ensure minimal food waste and maximum filled tummies to bed.This app provides a portal for restaurants to donate their unsold healthy food at the end of the day which can then be found by NGOs and then donated to the poor and needy. as simple as that." names="" pno="Project 2" imgsrc=""/>
        <ProjectCard pname1="DDoS Detection" pname2="and Mitigation" paragraph="An implementation of DDoS attack detection and mitigation using packet sniffing with Scapy in Python. It monitors incoming traffic and tracks packet counts from each IP within a time window. If an IP exceeds a set threshold, it's temporarily blocked using iptables, with automatic unblocking after a defined period." names="Andrea Tresa Tom, Annette George,Edwin Joseph,George Mathews, Ashwin MS,Tom Sibu" pno="Project 3" imgsrc=""/>
        <ProjectCard pname1="Helios" pname2="Browser" paragraph="" names="" pno="Project 4" imgsrc=""/>
    </div>
</div> -->
<script lang="ts">
    import ProjectCard from "$lib/components/projectcard.svelte";
    import { onMount } from 'svelte';
    import { gsap } from 'gsap';
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
    
    
    
    let container: HTMLElement;
    
    onMount(() => {
        gsap.registerPlugin(ScrollTrigger);
      const sections = gsap.utils.toArray('.project-card');
      
      gsap.to(sections, {
        xPercent: -100 * (sections.length - 1),
        ease: "none",
        scrollTrigger: {
          trigger: container,
          pin: true,
          scrub: 1,
          snap: 1 / (sections.length - 1),
          end: () => "+=" + container.offsetWidth
        }
      });
    });
    </script>
    
    <div class="h-screen overflow-hidden" bind:this={container}>
      <div class="flex">
        <div class="project-card">
          <ProjectCard pname1="HELIOS" pname2="BROWSER" paragraph="Helios Browser (previously known as project web) is an open source modular browser catered more towards developers, designers, and power users. It features functionalities meant to boost their workflow and automate many tasks." names="MILAN SUMAN,GAUTHAM SREERAM" pno="Project 1" imgsrc="/helios.jpg"/>
        </div>
        <div class="project-card">
          <ProjectCard pname1="DIAFA" pname2="SPACEAPP" paragraph="This a philanthropic project created for a hackathon. This projects connects restaurants and NGOs around the world to ensure minimal food waste and maximum filled tummies to bed.This app provides a portal for restaurants to donate their unsold healthy food at the end of the day which can then be found by NGOs and then donated to the poor and needy. as simple as that." names="" pno="Project 2" imgsrc=""/>
        </div>
        <div class="project-card">
          <ProjectCard pname1="DDoS Detection" pname2="and Mitigation" paragraph="An implementation of DDoS attack detection and mitigation using packet sniffing with Scapy in Python. It monitors incoming traffic and tracks packet counts from each IP within a time window. If an IP exceeds a set threshold, it's temporarily blocked using iptables, with automatic unblocking after a defined period." names="Andrea Tresa Tom, Annette George,Edwin Joseph,George Mathews, Ashwin MS,Tom Sibu" pno="Project 3" imgsrc=""/>
        </div>
        <div class="project-card">
          <ProjectCard pname1="Helios" pname2="Browser" paragraph="" names="" pno="Project 4" imgsrc=""/>
        </div>
      </div>
    </div>