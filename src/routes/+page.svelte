<script>
  import Navigation from "../components/Navigation.svelte";
import Image from "/src/CAI.png";
  import { onMount } from "svelte";

  let homeObject = {};

  onMount(async () => {
    try {
      const res = await fetch("http://34.201.108.35:1337/api/home", {
        headers: {
          authorization: `Bearer b62d2b9f8a64526c0501d2d82cb91c270a2e95a478677009dddb37414642d9850e62259336b2e372b6adcaa57f84f1c1d2bd542d3b0737c382785a0331afd0030a4f667b31cbbe71b13362bfd398e4eb2bf49aed4b5da038cbdd0f66b5cb5f57a4fbb64de2892df8d67b93d9c0a7f64eeaee33468127a1b238f0430e69af866c`,
        },
      });
      if (res.ok) {
        const home = await res.json();
        // console.log(home);
        homeObject = home.data.attributes;
      } else {
        console.error("Failed to fetch blog data");
      }
    } catch (error) {
      console.error("An error occurred:", error);
    }
  });
</script>

<div class="h-screen w-screen flex flex-col items-center justify-start bg-black text-white">
  <div class="max-w-[1440px] px-[4vw] py-6">
    <Navigation />
    <div
      class="w-full h-[720px] p-6 flex flex-col items-center justify-center gap-10"
    >
      <div class="w-[60rem] text-6xl font-bold text-center">
        {homeObject.hero_title}<span
          class="w-[60rem] text-6xl font-bold text-center text-[#6856F3]"
          >{homeObject.hero_title_keywords}</span
        >
      </div>
      <h2 class="w-[60rem] text-lg text-center">
        {homeObject.hero_description}
      </h2>
      <div class="w-[60rem] flex flex-row items-center justify-center gap-6">
        <button class="rounded-lg border-white border px-4 py-2"
          >{homeObject.button_1}</button
        >
        <button class="rounded-lg border-[#6856F3] border px-4 py-2"
          >{homeObject.button_2}</button
        >
      </div>
    </div>
  </div>
</div>
