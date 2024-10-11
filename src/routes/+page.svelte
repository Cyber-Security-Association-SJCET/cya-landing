<script lang="ts">
    import Globe from "$lib/components/globe.svelte"
    import {PersonStanding} from "lucide-svelte"
</script>

<main class="w-full min-h-screen flex flex-col text-white font-[Geist]">
    <nav class="flex flex-row p-6 border-b border-neutral-700 w-full items-center">
        <img src="/cya.webp" alt="Cyber Association" class="w-11 h-fit lg:w-14">
        <div class="md:flex flex-row items-center gap-6 ml-auto text-lg hidden">
            <a href="#test">About</a>
            <a href="#test">About</a>
            <a href="#test">About</a>
            <a href="#test">About</a>
        </div>
    </nav>
    <section id="home" class="flex flex-col p-8 gap-2 h-screen">
        <div class="flex flex-col gap-2 md:flex-row md:justify-between">
            <h1 class="text-2xl md:text-4xl lg:text-6xl font-bold md:w-1/3">WELCOME TO OUR CORNER OF THE INTERNET</h1>
            <p class="md:text-2xl md:text-right text-neutral-300"><bold class="font-bold">Cyber Security Association</bold><br>St. Joseph's College of Engineering and Technology, Palai</p>
        </div>
        <div class="w-full h-full absolute left-0 top-36 -z-10">
            <Globe/>
        </div>
    </section>
    <div class="flex flex-row p-6 border-b-2 border-t-2 border-neutral-700 backdrop-blur-lg">
        <a href="#" class="font-bold">Visit our blog!</a>
    </div>
    <section id="about" class="flex flex-col gap-2 h-screen">
        <div class="flex flex-row p-6 items-center">
            <h2 class="text-3xl font-bold">ABOUT</h2>
        </div>
        <div class="flex flex-col px-6 md:flex-row">
            <div class="flex flex-col p-6 rounded-t-2xl md:rounded-tr-none md:rounded-l-2xl border border-neutral-500 gap-3 md:w-1/2 min-h-72 justify-center" id="wormhole">
                <h2 class="font-bold text-5xl text-center font-[Jersey10]">VISION</h2>
                <p class="text-neutral-300">Developing into a world-class, pace-setting Institute of Engineering and Technology with distinct identity and character, meeting the goals and aspirations of the society.</p>
            </div>
            <div class="flex flex-col p-6 rounded-b-2xl md:rounded-r-2xl md:rounded-b-none border border-neutral-500 gap-3 md:w-1/2 min-h-72 justify-center" id="wormhole">
                <h2 class="font-bold text-5xl text-center font-[Jersey10]">MISSION</h2>
                <p class="text-neutral-300">
                    To maintain a conducive infrastructure and learning environment for world class education.
                    <br>
                    To nurture a team of dedicated, competent and research oriented faculty.
                    <br>
                    To develop students with moral & ethical values, for their successful career by offering variety of programmes and services.
                </p>
            </div>
        </div>
        <div class="flex flex-col px-6 md:flex-row">
            <div class="flex flex-col border border-neutral-500 rounded-t-2xl md:rounded-tr-none md:rounded-l-2xl flex-grow md:w-1/2">
                <p class="p-6 text-neutral-300 border-b border-neutral-500 flex-grow">
                    The Cyber Security Student Association at St. Joseph’s College of Engineering and Technology is a vibrant initiative aimed at enhancing student expertise in cybersecurity through hackathons, workshops, and seminars. By fostering collaboration and continuous learning, the association equips students to tackle complex challenges, engage with industry professionals, and participate in national and international competitions. It also promotes cybersecurity awareness within the academic community, helping students stay ahead of emerging threats and technologies.
                </p>
                <div class="flex flex-row">
                    <div class="p-3 flex-grow">

                    </div>
                    <div class="p-3 border-x border-neutral-500 flex-grow justify-center items-center">
                        <PersonStanding class="stroke-white mx-auto"/>
                    </div>
                    <div class="p-3 flex-grow border-r border-neutral-500 justify-center items-center">
                        <img src="/cya.webp" alt="Cyber Association" class="w-9 h-fit m-auto">
                    </div>
                    <div class="p-3 flex-grow text-center">
                        <p>ABOUT // CYA</p>
                    </div>
                </div>
            </div>
            <div class="flex flex-col items-center justify-center gap-10 border-x border-b border-neutral-500 p-6 font-[GajrajOne] md:border-t md:border-l-0 flex-grow">
                <h2 class="text-3xl text-center">WORLD ENCRYPTION DAY</h2>
                <h3 class="p-3 bg-slate-50 text-black w-fit text-2xl">OCTOBER 24</h3>
            </div>
            <div class="flex flex-row border-x border-b border-neutral-500 rounded-b-xl md:border-t md:flex-col md:rounded-r-2xl md:rounded-bl-none flex-grow">
                <div class="p-6 flex-grow">

                </div>
                <div class="p-6 border-l md:border-l-0 md:border-t border-neutral-500 flex-grow">

                </div>
            </div>
        </div>
    </section>
</main>

<style>
    #about-sjcet{
        background: no-repeat url("/sjcet.webp") center/cover;
    }

    #wormhole{
        background: no-repeat url("/wormhole.webp") center/cover;
    }
</style>
