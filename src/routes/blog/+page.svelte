<script>
  import Navigation from "../../components/Navigation.svelte";
import BlogPost from "../../components/blogPost.svelte";
  import Image from "/src/CAI.png";
</script>

<div
  class="h-screen w-screen flex flex-col items-center justify-start bg-black text-white overflow-x-hidden"
>
  <div class="max-w-[1440px] py-6">
    <Navigation />
    <h1 class="mb-[60px] text-4xl font-bold text-center">Blog</h1>
    <BlogPost />
  </div>
</div>
