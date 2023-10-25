<!-- ImageRightTextLeft.svelte -->
<script>
    export let body;
    export let imageUrl;
    export let compImage;
    // Add more props for the image later, if needed
  </script>
  
  <div class="w-full items-center justify-center flex flex-row pb-[30px]">
    <img class="m-w-1/2" src={compImage} alt="Description" />
    <p class="w-1/2 text-center">{body}</p>
  </div>
  