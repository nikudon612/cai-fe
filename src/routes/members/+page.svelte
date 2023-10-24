<script>
  import Members from "../../components/Members.svelte";
  import Image from "/src/CAI.png";
</script>

<div class="w-full py-6 flex flex-col p-[4vw]">
  <div class="flex flex-row">
      <a class="font-bold text-3xl" href="/"
        ><img src={Image} alt="" class="w-[15%] mb-[30px]" /></a
      >
      <div class="flex flex-row gap-6">
        <a class="text-xl" href="/blog"><h2>Blog</h2></a>
        <a class="text-xl" href="/test"><h2>Test</h2></a>
        <a class="text-xl" href="/members"><h2>Members</h2></a>
      </div>
    </div>
    <h1 class="mb-[60px] text-4xl font-bold">Featured Members</h1>
    <Members />
</div>