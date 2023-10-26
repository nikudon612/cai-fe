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

<div class="max-w-[100%] pb-24">
  <h2 class="text-sm mb-[30px]">{date}</h2>
  <a href={`/blog/${id}`} data={data}
    ><h1 class="text-3xl font-bold mb-[30px]">{title}</h1></a
  >
  <!-- Remove full markdown and show preview text -->
  <article class="w-full prose prose-lg mb-[30px] text-white opacity-60">
    <SvelteMarkdown {source} />
  </article>
  <a href={`/blog/${id}`} data={data}><p class="rounded-lg border-white border px-4 py-2 w-[135px] text-center">Read More</p></a>
</div>
