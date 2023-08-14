<script setup>
const heroData = ref({
  title: "WORKTECH",
  header: "The infrastructure of modern work",
  description:
    "Engineering new ways of connecting talents and organizations to enhance their financial performance and simplify compliance.",
  icon: "hero-icon.svg",
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
  <div
    class="py-[40px] px-[21.25px] md:py-[80px] md:px-[40px] flex flex-col bg-transparent border-b border-[#003e39] relative z-10"
  >
    <div class="flex items-start justify-between">
      <div class="flex flex-col gap-5 lg:flex-grow-0 lg:gap-16 lg:mb-10">
        <div class="font-medium">{{ heroData.title }}</div>
        <h1 class="mb-5 text-5xl font-bold md:text-[80px] md:leading-[1.2]">
          {{ heroData.header }}
        </h1>
        <p class="text-[20px] font-light leading-[1.5] mb-5 lg:">
          {{ heroData.description }}
        </p>
        <div class="flex flex-col gap-3 mb-12 md:mb-16 lg:flex-row">
          <ButtonSecondary>I'm a Talent</ButtonSecondary>
          <ButtonPrimary>I'm a Business</ButtonPrimary>
        </div>
      </div>
      <div
        class="items-start justify-start flex-grow hidden lg:flex lg:w-[900px]"
      >
        <NuxtImg :src="`/images/${heroData.icon}`" class="" />
      </div>
    </div>

    <div
      class="grid w-full grid-cols-2 gap-4 md:-bottom-[48px] md:grid-cols-4 md:absolute md:left-0 md:px-[40px]"
    >
      <div
        class="bg-[#F6F8FF] flex items-center justify-center lg:w-[200px] h-[100px] lg:h-[115px] shadow-[7px_7px_0px_0px_rgb(0,62,57)] ring-1 ring-[#003e39] rounded-md hover:shadow-[0px_0px_0px_0px_rgba(0,62,57,0)] transition-all hover:ring-0 duration-300 p-[24px]"
        v-for="sponsor in sponsors"
      >
        <NuxtImg
          :src="`/images/sponsors/${sponsor.icons}`"
          :alt="sponsor.title"
          class=""
        />
      </div>
    </div>
  </div>
</template>
