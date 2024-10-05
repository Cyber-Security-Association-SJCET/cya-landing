<script lang="ts">
    import Globe from "$lib/components/globe.svelte"
</script>

<main class="w-full min-h-screen bg-black flex flex-col text-white font-[Geist]">
    <nav class="absolute w-full flex flex-row gap-5 p-3 px-5 justify-evenly border-neutral-500 md:rounded-full md:w-fit md:border md:mx-auto md:mt-5 md:left-0 md:right-0 overflow-auto">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#achievements">Achievements</a>
        <a href="#events">Events</a>
    </nav>
    <section id="home" class="flex flex-col p-6 gap-2 md:flex-row md:items-center md:justify-center mt-[70px]">
        <div class="flex flex-col gap-2 w-full md:p-6 max-w-[600px]">
            <img src="/cya.webp" alt="Cyber Association" class="w-14">
            <h1 class="font-bold text-3xl lg:text-5xl">Welcome to the Cyber Security Association, SJCET</h1>
        </div>
        <div class="w-full aspect-square max-w-[600px]">
            <Globe/>
        </div>
    </section>
    <section id="about" class="flex flex-col p-6 gap-2">
        <div class="flex flex-col gap-3">
            <h1 class="font-bold text-2xl lg:text-4xl">Vision</h1>
            <p class="text-neutral-300">
                Developing into a world-class, pace-setting Institute of Engineering and Technology with distinct identity and character, meeting the goals and aspirations of the society.
            </p>
            <h1 class="font-bold text-2xl lg:text-4xl">Mission</h1>
            <p class="text-neutral-300">
                To maintain a conducive infrastructure and learning environment for world class education.

                To nurture a team of dedicated, competent and research oriented faculty.

                To develop students with moral & ethical values, for their successful career by offering variety of programmes and services.
            </p>
        </div>
    </section>
</main>
