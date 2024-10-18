<script lang="ts">
    type Project = {
        title: string;
        description: string;
        image?: string;
        authors: string[];
    }

    const projects: Project[] = [
        {
            title: "Project 1",
            description: "This is a project that does bla bla bla bla bla bla",
            authors: ["Person 1", "Person 2"]
        }
    ];
</script>

<div class="flex flex-col p-6 gap-4 max-w-96 aspect-square md:flex-row md:flex-wrap">
    <h1 class="text-3xl font-bold">PROJECTS</h1>
    {#each projects as project, index}
        <div class="flex flex-col rounded-md border border-neutral-500">
            <h3 class="p-4 border-b border-neutral-500 font-bold text-sm">
                Project {index+1}
            </h3>
            <div id="wormhole" class="p-4 border-b border-neutral-500">
                <h1 class="text-3xl font-bold">
                    {project.title}
                </h1>
                <p>
                    {project.authors.reduce((previous, current) => `${previous}, ${current}`)}
                </p>
            </div>
            <img src={project.image ?? "/wormhole.webp"} alt={project.title} class="w-full">
        </div>
    {/each}
</div>

<style>
    #wormhole{
        background: no-repeat url("/wormhole.webp") center/cover;
    }
</style>