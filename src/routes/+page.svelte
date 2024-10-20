<script lang="ts">
    import Globe from "$lib/components/globe.svelte";
    import Chessboard from "$lib/components/chessboard.svelte";
    import Twistysquare from "$lib/components/twistysquare.svelte";
    import Trafficlights from "$lib/components/trafficlights.svelte";
    import TextAnimation from "$lib/components/textanimation.svelte";
    import Achievements from "$lib/components/achievements.svelte";
    import { PersonStanding, Menu, X } from "lucide-svelte";
    import { onMount } from 'svelte';
    import 'aos/dist/aos.css';
    import AOS from 'aos';
    
   onMount(() => {
    AOS.init({
	easing: 'ease-out-back',
	duration: 1000,
    anchorPlacement: 'top-bottom'
});
   });
    let isMenuOpen = false;

    function toggleMenu() {
        isMenuOpen = !isMenuOpen;
    }
    
    import Textanimation from "$lib/components/textanimation.svelte";
</script>

<main class="w-full min-h-screen flex flex-col text-white font-[Geist] overflow-hidden">
    <nav class="flex flex-row p-6 border-b border-neutral-700 w-full items-center relative">
        <img src="/cya.webp" alt="Cyber Association" class="w-11 h-fit lg:w-14">
        <div class="md:flex flex-row items-center gap-6 ml-auto text-lg hidden">
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="/blog">Blog</a>
            <a href="#projects">Projects</a>
        </div>
        <button on:click={toggleMenu} class="ml-auto md:hidden">
            {#if isMenuOpen}
                <X class="stroke-white" />
            {:else}
                <Menu class="stroke-white" />
            {/if}
        </button>
        {#if isMenuOpen}
            <div class="absolute font-[jaro] top-full left-0 right-0 bg-black border-b border-neutral-700 md:hidden z-20">
                <div class="flex flex-col items-center gap-4 py-4">
                    <a href="#home" on:click={toggleMenu} class="pointer-events-auto">Home</a>
                    <a href="#about" on:click={toggleMenu} class="pointer-events-auto">About</a>
                    <a href="/blog" on:click={toggleMenu} class="pointer-events-auto">Blog</a>
                    <a href="#projects" on:click={toggleMenu} class="pointer-events-auto">Projects</a>
                </div>
            </div>
        {/if}
    </nav>

    <section id="home" class="flex flex-col p-8 gap-2 h-screen">
        <div class="flex flex-col gap-2 md:flex-row md:justify-between">
            <h1 class="text-2xl md:text-4xl lg:text-6xl font-bold md:w-1/3">WELCOME TO OUR CORNER OF THE INTERNET</h1>
            <p class="md:text-2xl md:text-right text-neutral-300">
                <strong class="font-bold">Cyber Security Association</strong><br>St. Joseph's College of Engineering and Technology, Palai
            </p>
        </div>
        <div class="w-full h-full absolute left-0 top-36 -z-10">
            <Globe/>
        </div>
    </section>

    <div class="flex flex-row p-6 border-b-2 border-t-2 border-neutral-700 backdrop-blur-lg">
        <a href="/blog" class="font-bold">Visit our blog!</a>
    </div>

    <section id="about" class="flex flex-col gap-2 min-h-screen" >
        <div class="flex flex-row p-6 items-center">
            <h2 class="text-3xl font-bold font-[FearLogo]">ABOUT</h2>
        </div>
        <div class="flex flex-col px-6 md:flex-row">
            <div class="flex flex-col p-6 rounded-t-2xl md:rounded-tr-none md:rounded-l-2xl border border-neutral-500 gap-3 md:w-1/2 min-h-72 justify-start items-center" data-aos="fade-up-right" id="wormhole">
                <h2 class="font-bold text-5xl text-center font-[Jersey10] tracking-wide">VISION</h2>
                <Textanimation text="To become a globally recognized hub of excellence in Cyber Security education and research, while upholding the distinctive values of the Institute."/>
            </div>
            <div class="flex flex-col p-6 rounded-b-2xl md:rounded-r-2xl md:rounded-b-none border border-neutral-500 gap-3 md:w-1/2 min-h-72 justify-start items-center " data-aos="fade-up-right" id="wormhole">
                <h2 class="font-bold text-5xl text-center font-[Jersey10] tracking-wide">MISSION</h2>

                <TextAnimation text="Education:To provide the comprehensive teaching of a cutting-edge and globally relevant curriculum in Cyber Security within a conducive and innovative learning environment."/>
                <TextAnimation text="Faculty Excellence:To cultivate a cadre of dedicated, highly competent, and research-driven faculty members, passionate about advancing the field of cybersecurity and delivering high-quality instructions."/>
                <TextAnimation text="Collaboration:To actively collaborate with industry leaders, organizations, and government agencies in the development and application of cybersecurity solutions, while ensuring our educational offerings meet the evolving needs of society."/>

            </div>
        </div>
        <div class="flex flex-col px-6 md:flex-row">
            <div class="flex flex-col border border-neutral-500 rounded-t-2xl md:rounded-tr-none md:rounded-l-2xl flex-grow md:w-1/2">
                <div class="p-6">
                    <TextAnimation text=" CYA is the student association of the CSE-CY department, focused on building a strong community of cybersecurity enthusiasts. The association's aim is to organize hackathons, events, and workshops that spread knowledge and help students develop their technical skills and stay updated with the latest trends in cybersecurity. CYA encourages students to collaborate and work on real-world problems through hands-on experiences. It serves as a platform for students to showcase their talents and prepare for future careers in this essential field. The association also strives to create a platform for cybersecurity awareness helping students stay ahead of emerging cyber threats and technologies"/>
                </div>
                
                <div class="flex flex-row mt-auto border-t border-neutral-500">
                    <div class="p-3 flex-grow flex justify-center items-center">
                        <Chessboard/>
                    </div>
                    <div class="p-3 border-x border-neutral-500 flex-grow flex justify-center items-center">
                        <PersonStanding class="stroke-white mx-auto"/>
                    </div>
                    <div class="p-3 flex flex-grow border-r border-neutral-500 justify-center items-center">
                        <img src="/cya.webp" alt="Cyber Association" class="w-9 h-fit m-auto">
                    </div>
                    <div class="p-3 flex-grow text-center">
                        <p>ABOUT // CYA</p>
                    </div>
                </div>
            </div>
            <div class="flex flex-col items-center justify-center gap-10 border-x border-b border-neutral-500 p-6 font-[FearLogo] md:border-t md:border-l-0 flex-grow">
                <p class="text-3xl text-center">WORLD ENCRYPTION DAY</p>
                <h3 class="p-3 bg-slate-50 rounded text-black w-fit text-2xl">OCTOBER 24</h3>
            </div>
            <div class="flex flex-row border-x border-b border-neutral-500 rounded-b-xl md:border-t md:flex-col md:rounded-r-2xl md:rounded-bl-none flex-grow " data-aos="flip-up">
                <div class="p-6 flex-grow flex items-center justify-center">
                    <Twistysquare/>
                </div>
                <div class="p-6 border-l md:border-l-0 md:border-t border-neutral-500 flex-grow flex items-center justify-center">
                    <Trafficlights/>
                </div>
            </div>
        </div>
    </section>

    <Achievements/>

    <section id="projects" class="flex flex-col gap-2 min-h-screen">
        <div class="flex flex-row p-6 items-center">
            <h2 class="text-4xl font-bold">PROJECTS</h2>
        </div>
        <div class="overflow-x-auto px-2 md:px-4 h-screen">
            <div class="flex flex-row gap-6">
                <div class="bg-black text-white rounded-3xl max-w-lg p-0 border border-gray-300 h-[745px] " data-aos="zoom-out-right">
                    <div class="p-3">
                        <h2 class="text-lg font-semibold">Project 1</h2>
                    </div>
                    <div class="flex flex-col p-6 justify-start border-t border-b border-white" id="wormhole">
                        <h1 class="text-6xl font-bold mb-2">HELIOS</h1>
                        <h1 class="text-6xl font-bold mb-4">BROWSER</h1>
                        <p class="text-lg mb-4">Milan Suman, Gautham Sreeram S B</p>
                    </div>
                    <p class="text-md p-6 border-b border-white">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec
                    </p>
                    <div class="relative overflow-hidden rounded-b-3xl">
                        <img
                            src="/helio_browser.png"
                            alt="Night scene with mountains, road, and moon"
                            class="w-full h-full object-cover"
                        />
                    </div>
                </div>
                <div class="bg-black text-white rounded-3xl max-w-lg p-0 border border-gray-300 h-[745px]" data-aos="zoom-out-up">
                    <div class="p-3">
                        <h2 class="text-lg font-semibold">Project 2</h2>
                    </div>
                    <div class="flex flex-col p-6 justify-start border-t border-b border-white" id="wormhole">
                        <h1 class="text-6xl font-bold mb-2">HELIOS</h1>
                        <h1 class="text-6xl font-bold mb-4">BROWSER</h1>
                        <p class="text-lg mb-4">Milan Suman, Gautham Sreeram S B</p>
                    </div>
                    <p class="text-md p-6 border-b border-white">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec
                    </p>
                    <div class="relative overflow-hidden rounded-b-3xl">
                        <img
                            src="/helio_browser.png"
                            alt="Night scene with mountains, road, and moon"
                            class="w-full h-full object-cover"
                        />
                    </div>
                </div>
                <div class="bg-black text-white rounded-3xl max-w-lg p-0 border border-gray-300 h-[745px]" data-aos="zoom-out-up">
                    <div class="p-3">
                        <h2 class="text-lg font-semibold">Project 3</h2>
                    </div>
                    <div class="flex flex-col p-6 justify-start border-t border-b border-white" id="wormhole">
                        <h1 class="text-6xl font-bold mb-2">HELIOS</h1>
                        <h1 class="text-6xl font-bold mb-4">BROWSER</h1>
                        <p class="text-lg mb-4">Milan Suman, Gautham Sreeram S B</p>
                    </div>
                    <p class="text-md p-6 border-b border-white">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec
                    </p>
                    <div class="relative overflow-hidden rounded-b-3xl">
                        <img
                            src="/helio_browser.png"
                            alt="Night scene with mountains, road, and moon"
                            class="w-full h-full object-cover"
                        />
                    </div>
                </div>
                <div class="bg-black text-white rounded-3xl max-w-lg p-0 border border-gray-300 h-[745px] " data-aos="zoom-out-left">
                    <div class="p-3">
                        <h2 class="text-lg font-semibold">Project 4</h2>
                    </div>
                    <div class="flex flex-col p-6 justify-start border-t border-b border-white" id="wormhole">
                        <h1 class="text-6xl font-bold mb-2">HELIOS</h1>
                        <h1 class="text-6xl font-bold mb-4">BROWSER</h1>
                        <p class="text-lg mb-4">Milan Suman, Gautham Sreeram S B</p>
                    </div>
                    <p class="text-md p-6 border-b border-white">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec imperdiet arcu eu sagittis accumsan. Nam
                        vehicula eget enim non dignissim. Nunc dapibus lobortis eros nec
                    </p>
                    <div class="relative overflow-hidden rounded-b-3xl">
                        <img
                            src="/helio_browser.png"
                            alt="Night scene with mountains, road, and moon"
                            class="w-full h-full object-cover"
                        />
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <footer class="w-full p-6">
        <div class="flex flex-col md:flex-row justify-between items-center md:pt-3">
            <div>
                <p>&copy; {new Date().getFullYear()} CYA SJCET | All rights reserved</p>
            </div>
            <div class="flex gap-4">
                <a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a>
                <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer">LinkedIn</a>
                <a href="https://instagram.com" target="_blank" rel="noopener noreferrer">Instagram</a>
            </div>
        </div>
    <footer class="w-full p-6 justify-center">
        
            <div class="">
                <div class="flex mx-auto justify-center items-center gap-6 p-6 ">
                    <div href="#"><img class=" md:w-35 md:h-35" src="/linkedin.png" alt="LinkedIn"></div>
                    <div href="#"><img class=" md:w-35 md:h-35" src="/twitter.png" alt="x(twitter)"></div>
                    <div href="#"><img class=" md:w-35 md:h-35" src="/github.png" alt="github"></div>
                    <div href="#"><img class=" md:w-35 md:h-35" src="/instagram.png" alt="instagram"></div>
                </div>
            </div>
            <div class="flex md:flex-col justify-between "><!--flex flex-col md:flex-row gap-4-->
                <div class="flex flex-col flex-wrap md:flex-row md:justify-center font-[FearLogo] md:items-center text-sm md:text-lg p-6 gap-6 md:gap-24">

                    <a href="#test">HOME</a>
                    <a href="#test">ABOUT</a>
                    <a href="#test">achievements</a>
                    <a href="#test">BLOG</a>
                    <a href="#test">PROJECTS</a>
                    
                </div>
                <div class="flex flex-col md:flex-row justify-center items-center p-4 gap-6 md:gap-36">
                    <img src="/cya.webp" alt="Cyber Association" class="w-20 md:w-26">
                    <img src="/sjcet-logo.webp" alt="SJCET PALAI" class="md:h-23 md:w-28 h-20 w-26">
                </div>
            </div>
    </footer>
</main>

<style>
    #about-sjcet {
        background: no-repeat url("/sjcet.webp") center/cover;
    }

    #wormhole {
        background: no-repeat url("/wormhole.webp") center/cover;
    }
</style>