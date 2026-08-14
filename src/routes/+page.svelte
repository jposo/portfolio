<script lang="ts">
    import { onMount } from "svelte";

    const me = {
        name: "Juan Osornio",
        role: "Data Engineer / Fullstack Developer",
        location: "United States / Mexico",
        thesis: "I build stuff that interests me & enjoy working on",
        email: "jposorniot@gmail.com",
        github: "https://github.com/jposo",
        linkedin: "https://linkedin.com/in/jposornio",
    };

    const projects = [
        {
            path: "~/work/01-levelswap",
            title: "LevelSwap",
            description: "Geometry Dash gamemode mod where players build and interchange what they build (similar to Gartic Phone)",
            tags: ["C++", "Go", "WebSocket"],
            href: "https://github.com/jposo/levelswap",
        },
        {
            path: "~/work/02-komga-ssr",
            title: "Komga SSR",
            description:
                "High-compatability Komga client which renders elements server-side.",
            tags: ["Go", "HTML"],
            href: "https://github.com/jposo/komga-ssr",
        },
        {
            path: "~/work/03-chip8-emulator",
            title: "Chip-8 Emulator",
            description:
                "Chip-8 emulator following a book's instructions, used to learn Rust + low-level understanding",
            tags: ["Rust", "Low-level", "WASM"],
            href: "https://github.com/jposo/chip8-emulator",
        },
    ];

    const skills = {
        "~/skills/data": ["Python", "Snowflake", "dbt"],
        "~/skills/frontend": ["Svelte / SvelteKit", "TypeScript", "Tailwind"],
        "~/skills/backend": ["Go", "Node.js", "Supabase", "Docker"],
        "~/skills/practice": [
            "Best practices",
            "Data structures",
            "Design systems",
        ],
        "~/skills/languages": ["English (fluent)", "Spanish (native)"],
    };
</script>

<svelte:head>
    <title>{me.name} — {me.role}</title>
</svelte:head>

<div
    data-theme="devlog"
    class="min-h-screen bg-base-100 text-base-content font-sans"
>
    <!-- Nav -->
    <header
        class="sticky top-0 z-30 border-b border-base-300 bg-base-100/90 backdrop-blur"
    >
        <nav
            class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between"
        >
            <a href="#top" class="font-mono text-sm text-primary"
                >/home/{me.name.toLowerCase().replace(" ", "-")}</a
            >
            <div
                class="hidden sm:flex items-center gap-6 font-mono text-sm text-info"
            >
                <a
                    href="#work"
                    class="hover:text-base-content transition-colors">~/work</a
                >
                <a
                    href="#skills"
                    class="hover:text-base-content transition-colors"
                    >~/skills</a
                >
                <a
                    href="#about"
                    class="hover:text-base-content transition-colors">~/about</a
                >
                <a
                    href="#contact"
                    class="btn btn-sm btn-outline border-primary text-primary hover:bg-primary hover:text-base-100"
                >
                    contact --me
                </a>
            </div>
        </nav>
    </header>

    <main id="top">
        <!-- Hero -->
        <section
            class="max-w-6xl mx-auto px-6 pt-16 pb-20 grid lg:grid-cols-[1.1fr_0.9fr] gap-12 items-start"
        >
            <div>
                <p class="font-mono text-sm text-secondary mb-3">
                    // {me.location}
                </p>
                <h1
                    class="font-mono text-4xl sm:text-5xl font-bold leading-tight mb-4"
                >
                    {me.name}
                </h1>
                <p class="text-lg text-info mb-6">{me.role}</p>
                <p
                    class="text-base text-base-content/80 max-w-lg mb-8 leading-relaxed"
                >
                    {me.thesis}
                </p>
                <div class="flex flex-wrap gap-3 font-mono text-sm">
                    <a href="#work" class="btn btn-primary btn-sm normal-case"
                        >view --work</a
                    >
                    <a
                        href="#contact"
                        class="btn btn-ghost btn-sm normal-case border border-base-300"
                    >
                        contact --me
                    </a>
                </div>
            </div>
        </section>

        <!-- Work -->
        <section
            id="work"
            class="max-w-6xl mx-auto px-6 py-16 border-t border-base-300"
        >
            <h2 class="font-mono text-sm text-primary mb-8">~/work</h2>
            <div class="grid sm:grid-cols-2 gap-5">
                {#each projects as project}
                    <a
                        href={project.href}
                        class="card bg-base-200 border border-base-300 hover:border-primary/60 transition-colors p-6 group"
                    >
                        <p class="font-mono text-xs text-info mb-2">
                            {project.path}
                        </p>
                        <h3
                            class="text-xl font-semibold mb-2 group-hover:text-primary transition-colors"
                        >
                            {project.title}
                        </h3>
                        <p
                            class="text-sm text-base-content/70 leading-relaxed mb-4"
                        >
                            {project.description}
                        </p>
                        <div class="flex flex-wrap gap-2">
                            {#each project.tags as tag}
                                <span
                                    class="badge badge-outline border-base-300 text-info font-mono text-xs"
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
            class="max-w-6xl mx-auto px-6 py-16 border-t border-base-300"
        >
            <h2 class="font-mono text-sm text-primary mb-8">~/skills</h2>
            <div class="grid sm:grid-cols-3 gap-8">
                {#each Object.entries(skills) as [path, items]}
                    <div>
                        <p class="font-mono text-xs text-info mb-3">{path}</p>
                        <ul class="space-y-2">
                            {#each items as item}
                                <li class="text-sm text-base-content/80">
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
            class="max-w-6xl mx-auto px-6 py-16 border-t border-base-300"
        >
            <h2 class="font-mono text-sm text-primary mb-8">~/about</h2>
            <div
                class="max-w-2xl space-y-4 text-base-content/80 leading-relaxed"
            >
                <p>
                    I've spent the last years learning, writing, & rewriting
                    code into what is best practice, and maintainable.
                    I'll occasioanally build a little tool that I need since the
                    alternatives don't hit.
                </p>
                <p>
                    I like making code that feels clean (clean repo is like a clean house).
                    If I don't understand what is going on, neither will the next engineer looking
                    at it.
                </p>
            </div>
        </section>
    </main>

    <!-- Contact / Footer -->
    <footer id="contact" class="border-t border-base-300">
        <div class="max-w-6xl mx-auto px-6 py-14">
            <h2 class="font-mono text-sm text-primary mb-6">~/contact</h2>
            <div class="flex flex-col gap-3 font-mono text-sm">
                <a
                    href={`mailto:${me.email}`}
                    class="hover:text-primary transition-colors focus-visible:outline-2 focus-visible:outline-primary"
                >
                    $ mail --to {me.email}
                </a>
                <a
                    href={me.github}
                    target="_blank"
                    rel="noreferrer"
                    class="hover:text-primary transition-colors focus-visible:outline-2 focus-visible:outline-primary"
                >
                    $ open {me.github.replace("https://", "")}
                </a>
                <a
                    href={me.linkedin}
                    target="_blank"
                    rel="noreferrer"
                    class="hover:text-primary transition-colors focus-visible:outline-2 focus-visible:outline-primary"
                >
                    $ open {me.linkedin.replace("https://", "")}
                </a>
            </div>
            <p class="mt-10 text-xs text-info/60 font-mono">
                // {new Date().getFullYear()}
                {me.name}
            </p>
        </div>
    </footer>
</div>
