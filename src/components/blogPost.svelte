<script>
  import { onMount } from "svelte";
  import Post from "./Post.svelte";

  let blogPosts = [];
  let title = "";
  let contents = "";
  let date = "";

  async function fetchData() {
    try {
      const res = await fetch(`http://34.201.108.35:1337/api/blogs`, {
        headers: {
          authorization: `Bearer b62d2b9f8a64526c0501d2d82cb91c270a2e95a478677009dddb37414642d9850e62259336b2e372b6adcaa57f84f1c1d2bd542d3b0737c382785a0331afd0030a4f667b31cbbe71b13362bfd398e4eb2bf49aed4b5da038cbdd0f66b5cb5f57a4fbb64de2892df8d67b93d9c0a7f64eeaee33468127a1b238f0430e69af866c`,
        },
      });

      if (res.ok) {
        const { data } = await res.json(); // Destructuring to get the data field
        console.log(data);

        // Mapping over the array of objects to transform it
        blogPosts = data.map((post) => ({
          title: post.attributes.Title,
          content: post.attributes.Content,
          date: post.attributes.Date,
          url: post.attributes.url,
          id: post.id,
        }));
      } else {
        console.error(`Failed to fetch data: ${res.status}`);
      }
    } catch (error) {
      console.error(`Error fetching data: ${error}`);
    }
  }

  onMount(() => {
    fetchData();
  });
</script>

<div class="w-full">
  {#each blogPosts as post}
    <div class="max-w-[1440px]">
        <Post title={post.title} content={post.content} date={post.date} url={post.url} id={post.id} data={post} />
    </div>
  {/each}
</div>
