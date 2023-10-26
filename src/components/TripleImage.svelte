<!-- ImageRightTextLeft.svelte -->
<script>
  export let body;
  export let compImage;
  export let Image2;
  export let Image3;
  export let RichText;

  import SvelteMarkdown from "svelte-markdown";

  let source = RichText;

  // Add more props for the image later, if needed
</script>

<div
  class="flex flex-col w-full h-full items-start justify-center pb-[200px]"
  style="display: flex; justify-content: space-between;"
>
  <article class="w-auto prose prose-lg mb-[100px] text-white opacity-60">
    <SvelteMarkdown {source} />
  </article>
  <div class="flex flex-row items-center justify-between gap-6">
    <img class="w-1/4" src={compImage} alt="Description" />
    <img class="w-1/4" src={Image2} alt="Description" />
    <img class="w-1/4" src={Image3} alt="Description" />
  </div>
</div>
