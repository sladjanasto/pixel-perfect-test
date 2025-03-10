<script>
    let images = [
      { src: "/images/person1.webp", alt: "Person 1" },
      { src: "/images/person2.webp", alt: "Person 2" },
      { src: "/images/person3.webp", alt: "Person 3" }
    ];
</script>
<div class=" relative flex">
    {#each images as img, i}
        <img src={img.src} alt={img.alt} class=" relative w-10 h-10 rounded-full border-solid border-2 border-[var(--bg-color-1)] -ml-[4px] " style="z-index: {30 - i}"  />
    {/each}
</div>