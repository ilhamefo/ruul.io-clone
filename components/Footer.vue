<script setup>
const footers = ref([
  {
    title: "For Talents",
    data: [
      "Global Invoicing",
      "Tax Assistance",
      "Payment Collection",
      "Banking (Coming Soon)",
    ],
  },
  {
    title: "For Businesses",
    data: ["AOR", "Payments", "Talent Management"],
  },
  {
    title: "Tools",
    data: ["Invoice Generator", "NDA Generator", "Service Agreement Generator"],
  },
  {
    title: "Resources",
    data: [
      "Pricing",
      "About",
      "Blog",
      "Support",
      "Contact Us",
      "Careers",
      "Download Press Kit",
    ],
  },
  {
    title: "Collaborate",
    data: [
      "Partners Program",
      "Partners",
      "Affiliate Program",
      "HR Affiliate Program",
      "Community",
    ],
  },
]);
</script>
<template>
  <div
    class="flex flex-col items-center justify-center bg-[#003e39] text-[#cafdc6] py-[40px] px-[21.25px] md:py-[120px] lg:py-[140px] md:px-[40px]"
  >
    <div class="container flex flex-col w-full gap-10">
      <div class="py-10">
        <NuxtImg
          src="/images/6400030a281a43b4c0c93c4a_Logo3.svg"
          class="w-[84px]"
        >
        </NuxtImg>
      </div>

      <div class="grid grid-cols-2 gap-8 border-b border-[#cafdc6] pb-14">
        <div
          :class="`flex flex-col items-start justify-start gap-2 `"
          v-for="(footer, i) in footers"
        >
          <div class="font-semibold">{{ footer.title }}</div>
          <button class="py-2 text-left" v-for="item in footer.data">
            {{ item }}
          </button>
        </div>
      </div>
    </div>
    <div class="container flex flex-col w-full gap-10 py-10">
      <div class="flex items-center justify-center ">
        <ButtonPrimary class="text-[#003e39] py-2 flex items-center justify-center gap-2 bg-[#cafdc6] px-10">
          <NuxtImg src="https://cdn.weglot.com/flags/circle/gb.svg" class="w-[18px]"></NuxtImg>
          <span class="text-base font-semibold">English</span>
        </ButtonPrimary>
      </div>
      <div class="">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex, dolorem.
      </div>
      <div class="">
        <FooterIcons />
      </div>
    </div>
  </div>
</template>
