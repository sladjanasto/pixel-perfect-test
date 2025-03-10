<script>
	import Content from "$lib/components/content.svelte";
	import Header from "$lib/components/header.svelte";
	import Heading from "$lib/components/heading.svelte";
	import Menu from "$lib/components/menu.svelte";

</script>
<div class="
        grid min-h-screen h-screen overflow-y-hidden mx-auto
        grid-rows-[minmax(0,105px)_auto_1fr_auto] 
        bg-[var(--color-primary)] bg-no-repeat 2xl:max-w-[1116px]
        before:absolute before:top-0 before:left-0 before:w-full before:h-1/2
        before:bg-[linear-gradient(to_bottom_right,var(--bg-color-1),var(--bg-color-2))]
        after:absolute after:top-1/2 after:left-0 after:w-full after:h-1/2
        after:bg-[linear-gradient(to_bottom_right,var(--bg-color-3),var(--bg-color-4))]">
    <Header />
    <Heading />
    <Content />
    <Menu />
</div>

