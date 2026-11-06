<script lang="ts">
    const me = {
        name: "Juan Osornio",
        location: "United States & Mexico",
        thesis: "Data Engineer and Software Developer",
        email: "jposorniot@gmail.com",
        github: "https://github.com/jposo",
        linkedin: "https://linkedin.com/in/jposornio",
    };

    const projects = [
        {
            title: "loggd",
            description:
                "A Letterboxd-style tracking and backlog platform for Geometry Dash levels.",
            tags: ["Svelte", "Supabase", "API"],
            href: "https://loggd.jposo.com",
        },
        {
            title: "Komga SSR",
            description:
                "High-compatability Komga client which renders elements server-side.",
            tags: ["Go", "HTML"],
            href: "https://github.com/jposo/komga-ssr",
        },
        {
            title: "Chip-8 Emulator",
            description:
                "Chip-8 emulator following a book's instructions, used to learn Rust + low-level understanding",
            tags: ["Rust", "Low-level", "WASM"],
            href: "https://github.com/jposo/chip8-emulator",
        },
    ];

    const skills = {
        Data: ["Python", "Snowflake", "dbt"],
        Frontend: ["Svelte / SvelteKit", "TypeScript", "Tailwind"],
        Backend: ["Go", "Node.js", "Supabase", "Docker"],
        Languages: ["English (fluent)", "Spanish (native)"],
    };
</script>

<svelte:head>
    <title>{me.name}</title>
</svelte:head>

<div>
    <main id="top">
        <section
            class="max-w-6xl mx-auto px-6 pt-16 grid lg:grid-cols-[1.1fr_0.9fr] gap-12 items-start"
        >
            <div>
                <p class="text-sm mb-3 text-[#5B3674]">
                    {me.location}
                </p>
                <h1 class="text-4xl sm:text-5xl font-bold mb-4">
                    {me.name}
                </h1>
                <p
                    class="text-base text-base-content/80 max-w-lg mb-8 leading-relaxed text-[#404850]"
                >
                    {me.thesis}
                </p>
            </div>
        </section>

        <!-- Work -->
        <section
            id="work"
            class="max-w-6xl mx-auto px-6 py-8 border-t border-base-300"
        >
            <h2 class="font-bold mb-8 text-[#007020]">Work</h2>
            <div class="grid sm:grid-cols-2 gap-5">
                {#each projects as project}
                    <a href={project.href} class="py-4 group">
                        <h3
                            class="text-xl font-semibold mb-2 group-hover:opacity-70 transition-opacity"
                        >
                            {project.title}
                        </h3>
                        <p class="text-sm leading-relaxed mb-4 text-[#404850]">
                            {project.description}
                        </p>
                        <div class="flex flex-wrap gap-2">
                            {#each project.tags as tag}
                                <span class="font-mono text-xs text-[#5B3674]"
                                    >{tag}</span
                                >
                            {/each}
                        </div>
                    </a>
                {/each}
            </div>
        </section>

        <!-- Skills -->
        <section
            id="skills"
            class="max-w-6xl mx-auto px-6 py-8 border-t border-base-300"
        >
            <h2 class="font-bold mb-8 text-[#007020]">Skills</h2>
            <div class="grid sm:grid-cols-3 gap-8">
                {#each Object.entries(skills) as [path, items]}
                    <div>
                        <p class="text-sm font-semibold mb-3 text-[#40A070]">
                            {path}
                        </p>
                        <ul class="space-y-2">
                            {#each items as item}
                                <li class="text-sm">
                                    {item}
                                </li>
                            {/each}
                        </ul>
                    </div>
                {/each}
            </div>
        </section>

        <!-- About -->
        <section
            id="about"
            class="max-w-6xl mx-auto px-6 py-8 border-t border-base-300"
        >
            <h2 class="font-bold mb-8 text-[#007020]">About</h2>
            <div
                class="max-w-2xl space-y-4 text-base-content/80 leading-relaxed"
            >
                <p>
                    I've spent the last years learning, writing, & rewriting
                    code into what is best practice, and maintainable. I'll
                    occasioanally build a little tool that I need since the
                    alternatives don't hit.
                </p>
                <p>
                    I like making code that feels clean (clean repo is like a
                    clean house). If I don't understand what is going on,
                    neither will the next engineer looking at it.
                </p>
            </div>
        </section>
    </main>

    <!-- Contact / Footer -->
    <footer id="contact" class="border-t border-base-300">
        <div class="max-w-6xl mx-auto px-6 py-7">
            <h2 class="font-bold mb-8 text-[#007020]">Contact</h2>
            <div class="flex flex-col gap-3 font-mono text-sm">
                <a
                    href={`mailto:${me.email}`}
                    class="hover:text-[#404850] transition-colors focus-visible:outline-2 focus-visible:outline-primary flex flex-row items-center gap-2"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="size-6"
                        viewBox="0 0 512 512"
                    >
                        <path d="M0 0h512v512H0z" fill="none" />
                        <path
                            fill="currentColor"
                            d="M424 80H88a56.06 56.06 0 0 0-56 56v240a56.06 56.06 0 0 0 56 56h336a56.06 56.06 0 0 0 56-56V136a56.06 56.06 0 0 0-56-56m-14.18 92.63l-144 112a16 16 0 0 1-19.64 0l-144-112a16 16 0 1 1 19.64-25.26L256 251.73l134.18-104.36a16 16 0 0 1 19.64 25.26"
                        />
                    </svg>
                    {me.email}
                </a>
                <a
                    href={me.github}
                    target="_blank"
                    rel="noreferrer"
                    class="hover:text-[#404850] transition-colors focus-visible:outline-2 focus-visible:outline-primary flex flex-row items-center gap-2"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="size-6"
                        viewBox="0 0 24 24"
                    >
                        <path d="M0 0h24v24H0z" fill="none" />
                        <path
                            fill="currentColor"
                            d="M8 20.156c-.765.029-1.529-.127-2.198-.506a4.7 4.7 0 0 1-1.069-.856a11 11 0 0 1-.729-.876q-.454-.588-.658-.76C3.25 17.076 3.131 17 3 17a1 1 0 0 1 0-2c1.221 0 1.915.826 2.587 1.696c.344.446.702.931 1.202 1.215c.369.209.793.27 1.211.243V18c0-.749.027-1.481.295-2.19c-2.083-.477-3.829-1.805-4.696-3.784C3.183 11.073 3 10.037 3 9c0-1.117.316-2.187.895-3.14c-.316-1.087-.242-2.183.177-3.231A1 1 0 0 1 5 2c.416 0 .833.067 1.241.141a16 16 0 0 1 2.832.814a13.1 13.1 0 0 1 5.854 0a16 16 0 0 1 2.832-.814C18.167 2.067 18.584 2 19 2c.409 0 .777.249.928.629c.419 1.048.493 2.144.177 3.231c.579.953.895 2.023.895 3.14c0 1.037-.183 2.073-.599 3.026c-.867 1.979-2.613 3.307-4.696 3.784c.268.709.295 1.441.295 2.19v3a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1Z"
                        />
                    </svg>

                    {me.github.replace("https://", "")}
                </a>
                <a
                    href={me.linkedin}
                    target="_blank"
                    rel="noreferrer"
                    class="hover:text-[#404850] transition-colors focus-visible:outline-2 focus-visible:outline-primary flex flex-row items-center gap-2"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="size-6"
                        viewBox="0 0 24 24"
                    >
                        <path d="M0 0h24v24H0z" fill="none" />
                        <path
                            fill="currentColor"
                            fill-rule="evenodd"
                            d="M9.429 8.969h3.714v1.85c.535-1.064 1.907-2.02 3.968-2.02c3.951 0 4.889 2.118 4.889 6.004V22h-4v-6.312c0-2.213-.535-3.461-1.897-3.461c-1.889 0-2.674 1.345-2.674 3.46V22h-4zM2.57 21.83h4V8.799h-4zM7.143 4.55a2.53 2.53 0 0 1-.753 1.802a2.57 2.57 0 0 1-1.82.748a2.6 2.6 0 0 1-1.818-.747A2.55 2.55 0 0 1 2 4.55c0-.677.27-1.325.753-1.803A2.58 2.58 0 0 1 4.571 2c.682 0 1.336.269 1.819.747s.753 1.126.753 1.803"
                            clip-rule="evenodd"
                        />
                    </svg>
                    {me.linkedin.replace("https://", "")}
                </a>
            </div>
        </div>
    </footer>
</div>
