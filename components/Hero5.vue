<script setup lang="ts">
const heroData = ref({
  title: "HERE TO HELP",
  header: "Common questions",
  description: "Find the answers to frequently asked questions here.",
  icon: "hero2-icon.svg",
  help: "Need further support?",
  buttonText: "Get Support",
});
</script>
<template>
  <div class="flex items-center justify-center border-b border-[#003e39] bg-[#F6F8FF]">
    <div
      class="py-[40px] px-[21.25px] md:py-[120px] lg:py-[140px] md:px-[40px] flex flex-col text-[#003e39] relative container-custom"
    >
      <div class="flex items-start justify-between lg:gap-x-14">
        <div class="flex flex-col w-full gap-3 lg:flex-row lg:mb-10">
          <div
            class="flex flex-col gap-3 lg:flex-grow-0 lg:gap-6 lg:mb-10 md:w-fit"
          >
            <div class="font-medium">{{ heroData.title }}</div>
            <h1
              class="text-5xl font-bold md:text-[78px] md:leading-[1.2] lg:text-[48px]"
            >
              {{ heroData.header }}
            </h1>
            <p class="text-[20px] leading-[1.5] my-2 font-medium">
              {{ heroData.description }}
            </p>
            <div
              class="flex flex-col md:flex-row lg:flex-col lg:items-start md:items-center md:gap-3"
            >
              <p class="leading-[1.5] my-2 font-medium text-base">
                {{ heroData.help }}
              </p>

              <ButtonSecondary class="py-4 md:py-3 lg:py-5">
                {{ heroData.buttonText }}
              </ButtonSecondary>
            </div>
          </div>
          <div class="flex flex-1">
            <FAQ class="w-full mt-10" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
