<script>
	import ActionArrowR from "$lib/icons/action-arrow-r.svelte";
	import ArrowRight from "$lib/icons/arrow-right.svelte";
	import Search from "$lib/icons/search.svelte";
    let topics = [
        { name: 'In-game bonuses and free spins', link: '#'},
        { name: 'Crypto deposit still not credited?', link: '#'},
        { name: 'Eiger X VIP program overview', link: '#'},
        { name: 'Achievements and awards', link: '#'}
    ];
    let searchQuery = '';
    $: filteredTopics = topics.filter( topic =>
        topic.name.toLocaleLowerCase().includes(searchQuery.toLocaleLowerCase())

    )
</script>
<div class="px-5 h-[calc(100%-115px)] relative">
    <div class="bg-[var(--bg-color-6)] p-2 rounded-lg grid grid-rows-[40px_auto_minmax(0,1fr)_auto] h-full">
        <div class="flex flex-row bg-[var(--bg-color-5)] items-center justify-center gap-5 px-3 rounded-md">
            <input type="text" placeholder="Search for help"
            bind:value={searchQuery}
             name="" id="" class="
                w-full p-0 text-sm font-[Inter] text-[var(--text-color)] bg-transparent
                border-none border-transparent focus:border-transparent outline-none focus:outline-none
                ring-0 focus:ring-0" 
                style="font-family: var(--font-inter);">
            <Search />
        </div>
        <div class='overflow-y-auto'>
            {#if filteredTopics.length > 0}
			{#each filteredTopics as topic}
				<a href="{topic.link}" class="
                    flex justify-between items-center px-3 py-2.5 rounded-md 
                    text-sm font-normal font-[Inter] text-[var(--text-color)] leading-[21px] 
                    hover:bg-[var(--bg-color-5)] transition
                ">
					<span>{topic.name}</span> 
					<ArrowRight />
				</a>
			{/each}
		{:else}
			<p class="text-gray-400 text-sm p-3">No results found</p>
		{/if}
        </div>
    </div>
</div>

