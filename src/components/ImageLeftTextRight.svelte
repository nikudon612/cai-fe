<script>
    export let body;
    export let compImage;
  </script>
  
  <div class="pb-[30px] w-full flex flex-row">
    <img class="w-1/2" src={compImage} alt="Section with image Description" />
    <p class="w-1/2 text-center">{body}</p>
  </div>
  