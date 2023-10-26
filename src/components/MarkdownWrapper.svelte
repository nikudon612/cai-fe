<!-- MarkdownWrapper.svelte -->
<script>
    import SvelteMarkdown from "svelte-markdown";
    export let source;
  </script>
  
  <article>
    <SvelteMarkdown {source} />
  </article>
  
  <style>
    /* Your custom styling here */
  </style>
  