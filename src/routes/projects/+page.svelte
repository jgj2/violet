<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";
    import { Badge } from "$lib/components/ui/badge";
    import * as Tabs from "$lib/components/ui/tabs/index.js";
	import ScrollArea from "$lib/components/ui/scroll-area/scroll-area.svelte";

    interface project {
        name: string;
        description: string;
        href: string;
        img: string;
        alt: string;
        tags: Array<string>;
    }

    const WIPProjects: Array<project> = [{
        name: 'Personal Site',
        description: 'My own personal website, a place designed to allow write ups and demonstrations of projects.',
        href: '/projects/personalsite',
        img: '/violet.png',
        alt: 'personal site',
        tags: ['web development', 'personal', 'svelte', 'sveltekit']
    }];

    const projects: Array<project> = [];
</script>

<svelte:head>
	<title>joseph james: projects</title>
	<meta name="description" content="a list of joseph james' projects" />
</svelte:head>


<Tabs.Root value="completed" class="h-full">
    <Tabs.List>
        <Tabs.Trigger value="completed">completed</Tabs.Trigger>
        <Tabs.Trigger value="wip">wip</Tabs.Trigger>
    </Tabs.List>
    <Tabs.Content value="completed">
        <ScrollArea>
            <ul class="grid grid-cols-1 gap-4 md:grid-cols-2 lg:grid-cols-3">
                {#each projects as project}
                <li class="cursor-pointer">
                    <a href={project.href}>
                        <Card.Root class="h-full flex flex-col shadow-stone-600 shadow-none hover:shadow-xs">
                            <Card.Title class="p-2">{project.name}</Card.Title>
                            <Card.Content class="flex flex-grow flex-col">
                                <img class="" src={project.img} alt={project.alt} />
                                {project.description}
                            </Card.Content>
                            <Card.Footer class="flex flex-wrap gap-2">
                                {#each project.tags as tag}
                                <Badge variant="secondary">{tag}</Badge>
                                {/each}
                            </Card.Footer>
                        </Card.Root>
                    </a>
                </li>
                {/each}
            </ul>
        </ScrollArea>
    </Tabs.Content>
    <Tabs.Content value="wip">
        <ScrollArea class="h-[calc(100vh-200px)]">
            <ul class="grid grid-cols-1 gap-4 md:grid-cols-2 lg:grid-cols-3">
            {#each WIPProjects as project}
            <li class="cursor-pointer">
                <a href={project.href}>
                    <Card.Root class="h-full flex flex-col shadow-stone-600 shadow-none hover:shadow-xs">
                        <Card.Title class="p-2">{project.name}</Card.Title>
                        <Card.Content class="flex flex-grow flex-col">
                            <img class="" src={project.img} alt={project.alt} />
                            {project.description}
                        </Card.Content>
                        <Card.Footer class="flex flex-wrap gap-2">
                            {#each project.tags as tag}
                            <Badge variant="secondary">{tag}</Badge>
                            {/each}
                        </Card.Footer>
                    </Card.Root>
                </a>
            </li>
            {/each}
        </ul>
        </ScrollArea>
    </Tabs.Content>
</Tabs.Root>