<script>
  import Members from "../../components/Members.svelte";
  import Navigation from "../../components/Navigation.svelte";
  import Image from "/src/CAI.png";
</script>

<div
  class="h-screen w-screen flex flex-col items-center justify-start bg-black text-white overflow-x-hidden"
>
  <div class="max-w-[1440px] py-6">
    <Navigation />
    <div class="mt-20">
      <h1 class="mb-[60px] text-4xl font-bold">Featured Members</h1>
      <Members />
    </div>
  </div>
</div>
