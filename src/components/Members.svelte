<script>
  const members = [
    {
      name: "adobe",
      image: "../adobe.jpeg",
    },
    {
    name: "afp",
      image: "../afp.jpeg",
    },
    {
    name: "ami",
      image: "../ami.jpeg",
    },
    {
        name: "anj",
      image: "../anj.jpeg",
    },
    {
        name: "ap",
      image: "../ap-2x.jpeg",
    },
    {
        name: "arm",
      image: "../arm.jpeg",
    },
  ];
</script>

<h2 class="text-xl font-bold text-left">Featured Members</h2>
<div class="flex flex-col items-center justify-start min-h-screen w-full py-6 p-[4vw]">
  <div class="w-[80%]">
    <div class="flex flex-nowrap overflow-x-auto">
      {#each members as member}
        <div class="w-[200px] h-[200px] flex p-4">
          <img
            src={member.image}
            alt="Member Image"
            class="max-w-full max-h-full object-contain"
          />
        </div>
      {/each}
    </div>
  </div>
</div>
