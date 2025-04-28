<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";
    import { Badge } from "$lib/components/ui/badge";
	import Button from "$lib/components/ui/button/button.svelte";
    import PixelarticonsGithub from '~icons/pixelarticons/github';

    const projects = [{
        name: 'Personal Site',
        description: 'My own personal website, a place designed to allow write ups and demonstrations of projects.',
        img: '/violet.png',
        alt: 'personal site',
        tags: ['web development', 'personal', 'svelte', 'sveltekit']
    }];

</script>

<svelte:head>
	<title>joseph james: projects</title>
	<meta name="description" content="a list of joseph james' projects" />
</svelte:head>

<article class="prose prose-slate dark:prose-invert">
    <h3>Personal Site</h3>
    <img src="/violet.png" alt="personal site"/>
    <h4>motivation</h4>
    <p>
        this site was made as part of an attempt to give myself somewhere to post + publicly demonstrate personal projects. the goal here is to expand and use this site as a playground of sorts, experimenting with web development in svelte + sveltekit, expanding my capabilities and, maybe, making something useful at some point.
    </p>
    <h4>technologies</h4>
    <p>
        site is built using:
    </p>
    <p>
        <Badge variant="secondary">
            <a href="https://svelte.dev/">svelte + sveltekit</a>
        </Badge>
        <Badge variant="secondary">
            <a href="https://tailwindcss.com/">tailwindcss</a>
        </Badge>
        <Badge variant="secondary">
            <a href="https://www.shadcn-svelte.com/">shadcn-svelte</a>
        </Badge>
    </p>
    <p>
        <Button variant="ghost" title="github" href="https://github.com/">
            <PixelarticonsGithub class="text-xl" alt="github"/>
        </Button>
    </p>
</article>