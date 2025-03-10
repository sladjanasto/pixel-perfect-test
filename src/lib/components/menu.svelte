<script lang=ts>
    import { onMount } from "svelte";
    import Home from "$lib/icons/home.svelte";
    import Messages from "$lib/icons/messages.svelte";
    import Help from "$lib/icons/help.svelte";

    const icons = {Home, Messages, Help};
    type IconName = keyof typeof icons;

    type MenuItem = {
    name: string;
    link: string;
    icon: IconName;
  };
    
    let menuItems: MenuItem[] = [
        {name: 'Home', link: '#home', icon: 'Home' },
        {name: 'Messages', link:'#messages', icon: 'Messages'},
        {name: 'Help', link:'#help', icon: 'Help'}
    ];
    // let activePath = window.location.pathname;
    let activeHash = typeof window !== "undefined" ? window.location.hash : "";

    onMount(() => {
    if (typeof window !== "undefined") {
        window.addEventListener("hashchange", () => {
            activeHash = window.location.hash;
        });
    }
});

    
</script>
<nav class="p-5 relative z-1">
    <ul class="flex justify-between rounded-lg bg-[var(--bg-color-1)]">
        {#each menuItems as item}
        <li class='font-[Inter]   w-full  '>
            <a class=" 
                flex flex-col items-center gap-2 p-5 text-sm 
                font-semi-bold leading-tight translation-colors duration-300 
                { activeHash === item.link ? 'text-[var(--color-primary)]': 'text-[var(--text-color)] hover:text-[var(--color-primary)]'}" 
                 href="{item.link}">
                <svelte:component this={icons[item.icon]} class=
                    {"w-5 h-5 text-current " + (activeHash === item.link ? "fill-[var(--color-primary)]" : "fill-[var(--text-color)] hover:fill-[var(--color-primary)]")} />
                {item.name}
            </a>
        </li>
        {/each}
    </ul>
</nav>