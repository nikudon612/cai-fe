<script>
  import { onMount } from "svelte";
  import Image from "/src/CAI.png";
  import RenderComponent from "../../components/RenderComponent.svelte";
  import Navigation from "../../components/Navigation.svelte";

  let testData = [];

  async function fetchData() {
    try {
      const res = await fetch(
        `http://34.201.108.35:1337/api/test-collections?populate[0]=Bodypopulate[Body]&populate[1]=Body.image&populate[2]=Body.image.media&populate[3]=Body.image2&populate[4]=Body.image2.media&populate[5]=Body.image3&populate[6]=Body.image3.media`,
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
        console.log(testData[0].attributes.Body[2].image.data.attributes.url);
        console.log(testData[0].attributes.Body[3].image)
        console.log(testData[0].attributes.Body[3].image2)
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

<div
  class="h-screen w-screen flex flex-col items-center justify-start bg-black text-white overflow-x-hidden"
>
  <div class="max-w-[1440px] py-6">
    <Navigation />
    <!-- Rendering dynamic components -->
    {#if testData.length > 0}
      <div />
      {#each testData as post}
        <div class="px-6 mt-20">
          <div class="pb-[30px]">
            <h1 class="text-3xl font-bold">{post.attributes.Title}</h1>
            <p class="text-sm">{post.attributes.Summary}</p>
          </div>
          <div class="">
            {#each post.attributes.Body as bodyItem, index}
              <RenderComponent
                {bodyItem}
                compImage={bodyItem?.image?.data?.attributes?.url}
                Image2={bodyItem?.image2?.data?.attributes?.url}
                Image3={bodyItem?.image3?.data?.attributes?.url}
              />
            {/each}
          </div>
        </div>
      {/each}
    {:else}
      <p>Loading...</p>
    {/if}
  </div>
</div>
