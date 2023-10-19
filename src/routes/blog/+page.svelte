<script>
  import BlogPost from "../../components/blogPost.svelte";
  import Image from "/src/CAI.png";
</script>

<div class="w-full py-6 flex flex-col p-[4vw]">
  <div class="flex flex-row items-center justify-between w-full mb-[30px]">
    <a class="font-bold text-3xl" href="/"><img src={Image} alt="" class="w-[15%]" /></a>
  </div>
  <h1 class="mb-[60px] text-4xl font-bold">Blog</h1>
  <BlogPost />
</div>
