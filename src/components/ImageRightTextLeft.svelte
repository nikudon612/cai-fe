<!-- ImageRightTextLeft.svelte -->
<script>
  export let body;
  export let compImage;
  export let Image2;
  export let RichText;

  import SvelteMarkdown from "svelte-markdown";

  // let source = body;
  let source = RichText;

  // Add more props for the image later, if needed
</script>

<div
  class="w-full h-full items-start justify-center pb-[200px]"
  style="display: flex; justify-content: space-between;"
>
  <article class="w-auto prose prose-lg mb-[30px] text-white opacity-60">
    <SvelteMarkdown {source} />

  </article>
  <img class="w-1/3" src={compImage} alt="Description" />
</div>
