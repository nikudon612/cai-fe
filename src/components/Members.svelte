<script>
  const members = [
    {
      image: "../adobe.jpeg",
    },
    {
      image: "../afp.jpeg",
    },
    {
      image: "../ami.jpeg",
    },
    {
      image: "../anj.jpeg",
    },
    {
      image: "../ap-2x.jpeg",
    },
  ];
</script>

<div>
  <h2 class="text-xl font-bold">Featured Members</h2>
  <div class="flex flex-row">
    {#each members as member}
      <div class="flex flex-row aspect-square">
        <img src={member.image} class="aspect-square max-h-[80px] max-w-[80px]" />
      </div>
    {/each}
  </div>
</div>
