<!-- ImageRightTextLeft.svelte -->
<script>
    export let body;
    export let imageUrl;
    export let compImage;
    // Add more props for the image later, if needed
  </script>
  
  <div class="items-center justify-center pb-[30px]" style="display: flex; justify-content: space-between;">
    <p>{body}</p>
    <img src={compImage} alt="Description" />
  </div>
  