<script setup lang="ts">

const heroData = ref({
  title: "HERE TO HELP",
  header: "Common questions",
  description:
    "Find the answers to frequently asked questions here.",
  icon: "hero2-icon.svg",
  help:"Need further support?",
  buttonText: "Get Support",
});

</script>
<template>
  <div
    class="py-[40px] px-[21.25px] md:py-[120px] lg:py-[140px] md:px-[40px] flex flex-col bg-[#F6F8FF] text-[#003e39] relative border-b border-[#003e39]"
  >

    <div class="flex items-start justify-between lg:gap-x-14">
      <div class="flex flex-col gap-3 lg:flex-grow-0 lg:gap-6 lg:mb-10">
        <div class="font-medium ">{{ heroData.title }}</div>
        <h1
          class=" text-5xl font-bold md:text-[78px] md:leading-[1.2] lg:text-[48px] "
        >
          {{ heroData.header }}
        </h1>
        <p class="text-[20px] leading-[1.5] my-2 font-medium">
          {{ heroData.description }}
        </p>
        <div class="flex flex-col md:flex-row md:items-center md:gap-3">
          <p class="leading-[1.5] my-2 font-medium text-base">
            {{ heroData.help }}
          </p>
          
          <ButtonSecondary class="py-4 md:py-3">{{ heroData.buttonText }}</ButtonSecondary>
        </div>

        <FAQ class="mt-10" />
      </div>
    </div>
  </div>
</template>
