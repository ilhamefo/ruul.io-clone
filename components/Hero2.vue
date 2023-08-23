<script setup>
const heroData = ref({
  title: "Agency of Record",
  header: "A new connection protocol for work",
  description:
    "Say goodbye to the old and outdated payroll system. Modern work demands a new employment protocol between talents and businesses. Ruul pioneers this revolutionary transformation.",
  icon: "hero2-icon.svg",
  keys: [
    {
      icon: "hero2-icon-1.svg",
      title: "Streamlined compliance",
      description:
        "Remain compliant with local regulations with zero paperwork.",
    },
    {
      icon: "hero2-icon-2.svg",
      title: "Financial enhancement",
      description:
        "Ease off your payroll burden with a lighter connection protocol.",
    },
    {
      icon: "hero2-icon-3.svg",
      title: "Easy attachment & detachment",
      description:
        "The agile connection protocol for engaging with your workforce.",
    },
    {
      icon: "hero2-icon-4.svg",
      title: "Cross-border standardization",
      description:
        "International work arrangements simplified for global businesses.",
    },
  ],
});

const sponsors = ref([
  {
    icons: "sponsor-1.png",
    title: "Klarna",
  },
  {
    icons: "sponsor-2.png",
    title: "Toyota",
  },
  {
    icons: "sponsor-3.png",
    title: "Intel Insider",
  },
  {
    icons: "sponsor-4.png",
    title: "MIT",
  },
]);
</script>
<template>
  <div class="flex items-center justify-center bg-[#F6F8FF] border-b border-[#003e39]">
    <div
      class="py-[40px] px-[21.25px] md:py-[80px] lg:py-[140px] md:px-[40px] flex flex-col  relative container"
    >
      <div class="flex items-start justify-between lg:gap-x-14">
        <div
          class="items-start justify-start flex-grow hidden lg:flex lg:w-[900px]"
        >
          <NuxtImg :src="`/images/hero/${heroData.icon}`" class="" />
        </div>
        <div class="flex flex-col gap-5 lg:flex-grow-0 lg:gap-6 lg:mb-10">
          <div class="font-medium">{{ heroData.title }}</div>
          <h1
            class="mb-5 text-5xl font-bold md:text-[80px] md:leading-[1.2] lg:text-[48px]"
          >
            {{ heroData.header }}
          </h1>
          <p class="text-[20px] font-light leading-[1.5] mb-5 lg:">
            {{ heroData.description }}
          </p>

          <div
            class="flex flex-row items-center justify-start gap-3 mb-12 md:mb-16 lg:flex-row bg-[#feefca] rounded-md ring-1 ring-[#003e39] p-3"
          >
            <div class="flex flex-col">
              <div
                class="flex-grow w-6 h-6 rounded-full bg-[#003e39] flex items-center justify-center"
              >
                <IconsBulp class="fill-[#feefca]" />
              </div>
            </div>
            <div class="flex-grow-0">
              Agency of Record (AOR) service enables off-payroll talents and
              organizations to work together in a streamlined and compliant
              manner, simplifying cross-border work relations for both parties.
            </div>
          </div>

          <div class="grid grid-cols-1 gap-10 md:grid-cols-2">
            <div
              class="flex items-start justify-start gap-5"
              v-for="item in heroData.keys"
            >
              <div class="flex flex-col">
                <div
                  class="bg-[#F6F8FF] rounded-full ring-1 ring-[#003e39] shadow-[4px_4px_0px_0px_rgb(0,62,57)] w-[48px] h-[48px] flex flex-col items-center justify-center"
                >
                  <NuxtImg
                    :src="`/images/hero/${item.icon}`"
                    class="w-[24px]"
                  />
                </div>
              </div>
              <div class="flex flex-col items-start justify-start flex-grow-0">
                <div class="text-[22px] font-semibold line-clamp-1">
                  {{ item.title }}
                </div>
                <div class="text-[20px]">{{ item.description }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
