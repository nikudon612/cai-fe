<script>
    import { onMount } from "svelte";
    let membersData = [];
  
    onMount(async () => {
      try {
        const res = await fetch('http://34.201.108.35:1337/api/memberships', {
          headers: {
            authorization: `Bearer b62d2b9f8a64526c0501d2d82cb91c270a2e95a478677009dddb37414642d9850e62259336b2e372b6adcaa57f84f1c1d2bd542d3b0737c382785a0331afd0030a4f667b31cbbe71b13362bfd398e4eb2bf49aed4b5da038cbdd0f66b5cb5f57a4fbb64de2892df8d67b93d9c0a7f64eeaee33468127a1b238f0430e69af866c`,
          },
        });
        
        if (res.ok) {
          const allMembers = await res.json();
          const membersMap = allMembers.data.map((member) => {
            return {
              name: member.attributes.Name,
              image: member.attributes.Image,
              id: member.id,
            };
          });
          membersData = membersMap;
        } else {
          console.error('Failed to fetch blog data');
        }
      } catch (error) {
        console.error('An error occurred:', error);
      }
    });
  </script>
  
  <div class="flex flex-col items-center justify-start min-h-screen w-full py-6 p-[4vw]">
    <div class="w-[80%]">
      <div class="flex flex-nowrap overflow-x-auto">
        {#each membersData as member}
          <div>{member.name}</div>
        {/each}
      </div>
    </div>
  </div>
  