<script>
  // @ts-nocheck
  import SvelteMarkdown from "svelte-markdown";

  export let title;
  export let content;
  export let date;
  export let url;
  export let data;
  export let id;

  let source = content;
</script>

<div class="max-w-[72%] pb-24">
  <h2 class="text-sm mb-[30px]">{date}</h2>
  <a href={`/blog/${id}`} data={data}
    ><h1 class="text-3xl font-bold mb-[30px]">{title}</h1></a
  >
  <!-- Remove full markdown and show preview text -->
  <article class="w-full prose prose-lg mb-[30px]">
    <SvelteMarkdown {source} />
  </article>
  <a href={`/blog/${id}`} data={data}><p class="text-xl underline">Read More</p></a>
  <!-- Insert Preview Image -->
</div>
