<script>
  import { onMount } from "svelte";
  import Image from "/src/CAI.png";
  import RenderComponent from "../../components/RenderComponent.svelte";

  let testData = [];

  async function fetchData() {
    try {
      const res = await fetch(
        `http://34.201.108.35:1337/api/test-collections?populate[0]=Bodypopulate[Body]&populate[1]=Body.image&populate[2]=Body.image.media`,
        {
          headers: {
            authorization: `Bearer b62d2b9f8a64526c0501d2d82cb91c270a2e95a478677009dddb37414642d9850e62259336b2e372b6adcaa57f84f1c1d2bd542d3b0737c382785a0331afd0030a4f667b31cbbe71b13362bfd398e4eb2bf49aed4b5da038cbdd0f66b5cb5f57a4fbb64de2892df8d67b93d9c0a7f64eeaee33468127a1b238f0430e69af866c`,
          },
        }
      );

      if (res.ok) {
        const { data } = await res.json();
        testData = data;
        console.log(testData);
        console.log(testData[0].attributes.Body[0].body);
        console.log(testData[0].attributes.Body[2].image.data.attributes.url)
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

<div class="w-full py-6 flex flex-col p-[4vw]">
  <div class="flex flex-row">
    <a class="font-bold text-3xl" href="/"
      ><img src={Image} alt="" class="w-[15%] mb-[30px]" /></a
    >
    <div class="flex flex-row gap-6">
      <a class="text-xl" href="/blog"><h2>Blog</h2></a>
      <a class="text-xl" href="/test"><h2>Test</h2></a>
      <a class="text-xl" href="/members"><h2>Members</h2></a>
    </div>
  </div>
  <h1 class="mb-[60px] text-4xl font-bold">Test</h1>
</div>

<!-- Rendering dynamic components -->
{#if testData.length > 0}
  <div />
  {#each testData as post}
    <div class="px-6">
      <div class="pb-[30px]">
        <h1 class="text-3xl font-bold">{post.attributes.Title}</h1>
        <p class="text-sm">{post.attributes.Summary}</p>
      </div>
      <div class="">
        {#each post.attributes.Body as bodyItem, index}
        <RenderComponent {bodyItem} compImage={bodyItem?.image?.data?.attributes?.url} />
      {/each}
      </div>
    </div>
  {/each}
{:else}
  <p>Loading...</p>
{/if}
