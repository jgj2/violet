<script lang="ts">
	import {mode, toggleMode} from "mode-watcher";
	import { Button } from "$lib/components/ui/button";
	import Separator from "../separator/separator.svelte";
    import PhHamburgerThin from '~icons/ph/hamburger-thin';
    import * as Sheet from "$lib/components/ui/sheet";
    import { beforeNavigate } from "$app/navigation";

    let isOpen = $state(false);
    beforeNavigate(() => {
        isOpen = false;
    });
</script>

<nav class="w-full flex justify-between items-center p-2 spacing-x-2">
    <div>
        <a href="/">
            <h1 class="text-xl">
                joseph james
            </h1>
            <h2>software developer</h2>
        </a>
    </div>
    <div class="flex-row hidden md:flex">
        <Button href="/" variant="link" class="text-lg">
            home
        </Button>
        <Separator orientation="vertical"/>
        <Button href="/projects" variant="link" class="text-lg">
            projects
        </Button>
        <Separator orientation="vertical"/>
        <!--
        <Button href="/dotfiles" variant="link" class="text-lg">
            dot files
        </Button>
        <Separator orientation="vertical"/>
        <Button href="/vimconfig" variant="link" class="text-lg">
            vim config
        </Button>
        <Separator orientation="vertical" />
    -->
        <Button variant="link" onclick={toggleMode} class="text-lg cursor-pointer">
            {$mode}
        </Button>
    </div>
    <div class="md:hidden">
        <Sheet.Root bind:open={isOpen}>
            <Sheet.Trigger asChild let:builder>
                <Button builders={[builder]} variant="ghost" size="icon" class="m-2 cursor-pointer">
                    <PhHamburgerThin class="text-3xl" alt="menu button"/>
                </Button>
            </Sheet.Trigger>
            <Sheet.Content>
                <Button href="/" variant="link" class="text-lg">
                    home
                </Button>
                <Separator orientation="horizontal"/>
                <Button href="/projects" variant="link" class="text-lg">
                    projects
                </Button>
                <Separator />
                <Button variant="link" onclick={toggleMode} class="text-lg cursor-pointer">
                    {$mode}
                </Button>
            </Sheet.Content>
        </Sheet.Root>
    </div>
</nav>
<Separator class="h-[4px]" />