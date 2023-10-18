<script>
  import { onMount } from "svelte";
  import { page } from "$app/stores";

  let blogData = null;
  let formattedDate = "";
  const blogId = $page.params.id;

  function formatDate(isoString) {
  const datePortion = isoString.split("T")[0]; // Extract 'YYYY-MM-DD'
  const [year, month, day] = datePortion.split("-");
  return `${month}/${day}/${year}`;
}

  //Fetch individual blog post by ID
  onMount(async () => {
    try {
      const res = await fetch(`http://34.201.108.35:1337/api/blogs`, {
        headers: {
          authorization: `Bearer b62d2b9f8a64526c0501d2d82cb91c270a2e95a478677009dddb37414642d9850e62259336b2e372b6adcaa57f84f1c1d2bd542d3b0737c382785a0331afd0030a4f667b31cbbe71b13362bfd398e4eb2bf49aed4b5da038cbdd0f66b5cb5f57a4fbb64de2892df8d67b93d9c0a7f64eeaee33468127a1b238f0430e69af866c`,
        },
      });
      if (res.ok) {
        const allBlogs = await res.json();
        blogData = allBlogs.data.find((blog) => blog.id === parseInt(blogId));

        if (blogData) {
          blogData = blogData.attributes; // Access the 'attributes' object
          formattedDate = formatDate(blogData.Date); // Call the formatDate function
        }
      } else {
        console.error("Failed to fetch blog data");
      }
    } catch (error) {
      console.error("An error occurred:", error);
    }
  });
</script>

<div class="p-[4vw]">
  {#if blogData}
    <p class="text-sm mb-[30px] text-gray-800">{formattedDate}</p>
    <h1 class="text-5xl font-bold mb-[30px]">{blogData.Title}</h1>
    <!-- Note that keys are case-sensitive -->
    <p class="leading-6">{blogData.Content}</p>
    <!-- render other attributes here -->
  {:else}
    <p>Loading...</p>
  {/if}
</div>
