<!-- ImageRightTextLeft.svelte -->
<script>
    export let body;
    export let imageUrl;
    // Add more props for the image later, if needed
  </script>
  
  <div style="display: flex; justify-content: space-between;">
    <p>{body}</p>
    <img src={imageUrl} alt="Description" />
  </div>
  