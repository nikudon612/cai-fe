<script>
  import Navigation from "../../components/Navigation.svelte";
import BlogPost from "../../components/blogPost.svelte";
  import Image from "/src/CAI.png";
</script>

<svelte:head>
  <title>CAI | Blog</title>
  <meta name="description" content="CAI Blog" />
</svelte:head>

<div
  class="h-screen w-screen flex flex-col items-center justify-start bg-black text-white overflow-x-hidden"
>
  <div class="max-w-[1440px] py-6">
    <Navigation />
    <div class="mt-20">
      <BlogPost  />
    </div>
  </div>
</div>
