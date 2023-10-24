<!-- SectionWithImage.svelte -->
<script>
    export let body;
    export let imageUrl;
  </script>
  
  <div>
    <img src={imageUrl} alt="Secttion with image Description" />
    <p>{body}</p>
  </div>
  