<!-- Example: SectionWithImage.svelte -->
<script>
    export let body;
    export let compImage;
  </script>
  
  <div class="pb-[30px]">
    <img src={compImage} alt="Section with image Description" />
    <p>{body}</p>
  </div>
  