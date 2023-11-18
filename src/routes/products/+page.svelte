<script>
  import Card from "$lib/components/Card.svelte"

  let cardData = [
    {src: "/images/img1.jpg", alt: "a computer related image"},
    {src: "/images/img2.jpg", alt: "a computer related image"},
    {src: "/images/img3.jpg", alt: "a computer related image"},
    {src: "/images/img4.jpg", alt: "a computer related image"},
    {src: "/images/img5.jpg", alt: "a computer related image"},
    {src: "/images/img6.jpg", alt: "a computer related image"},
    {src: "/images/img7.jpg", alt: "a computer related image"},
    {src: "/images/img8.jpg", alt: "a computer related image"}
    ]
</script>

<main class="flex gap-10 justify-center my-20 p-5 flex-wrap">
  {#each cardData as card}
    <Card {...card} />
  {/each}
</main>