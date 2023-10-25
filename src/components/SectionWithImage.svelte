<!-- SectionWithImage.svelte -->
<script>
    export let body;
    export let imageUrl;
    export let compImage;
  </script>
  
  <div class="pb-[30px]">
    <img src={compImage} alt="Secttion with image Description" />
    <p>{body}</p>
  </div>
  