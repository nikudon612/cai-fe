<!-- ImageRightTextLeft.svelte -->
<script>
    export let body;
    export let compImage;
    // Add more props for the image later, if needed
  </script>
  
  <div class="w-full items-center justify-center pb-[30px]" style="display: flex; justify-content: space-between;">
    <p class="w-1/2 text-center">{body}</p>
    <img class="w-1/2" src={compImage} alt="Description" />
  </div>
  