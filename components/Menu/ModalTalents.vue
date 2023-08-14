<script setup>
const menuData = ref([
  {
    icon: "icon-1.svg",
    title: "Global Invoicing",
    subtitle: "Invoice globally without a legal entity.",
  },
  {
    icon: "icon-2.svg",
    title: "Tax Assistance",
    subtitle: "Ensure talent-friendly accounting and tax filing.",
  },
  {
    icon: "icon-3.svg",
    title: "Payment Collection",
    subtitle: "Collect fast and secure global payments.",
  },
  {
    icon: "icon-4.svg",
    title: "Banking (Coming Soon)",
    subtitle: "Zero-fee, borderless banking for solo talents.",
  },
]);

const heroData = ref({
  image: "icon-16.svg",
  title: "Ruul For Talents",
  subtitle:
    "A new connection protocol for modern talents to connect with businesses globally.",
  button: "See all talent solutions",
});
</script>
<template>
  <div
    class="bg-[#F6F8FF] w-full top-14 border rounded-lg border-[#003e39] shadow-[0_2.8px_2.2px_rgba(0,_0,_0,_0.034),_0_6.7px_5.3px_rgba(0,_0,_0,_0.048),_0_12.5px_10px_rgba(0,_0,_0,_0.06),_0_22.3px_17.9px_rgba(0,_0,_0,_0.072),_0_41.8px_33.4px_rgba(0,_0,_0,_0.086),_0_100px_80px_rgba(0,_0,_0,_0.12)] overflow-hidden"
  >
    <div class="flex flex-col md:gap-y-5 lg:flex-row">
      <div class="md:bg-[#C9FEC6] flex flex-col gap-y-5 p-4 md:p-8 lg:border-r lg:border-[#003e39]">
        <div class="text-[#003e39] text-4xl font-semibold hidden md:flex">
          {{ heroData.title }}
        </div>
        <div class="text-[#003e39] hidden md:flex">
          {{ heroData.subtitle }}
        </div>

        <div class="hidden rounded-lg overflow-clip lg:flex">
          <NuxtImg :src="`/images/menu/${heroData.image}`"/>
        </div>

        <ButtonSecondary class="md:w-fit lg:w-full">
          <span class="font-medium text-white">{{ heroData.button }}</span>
        </ButtonSecondary>
      </div>

      <div class="grid grid-cols-1 p-4 md:grid-cols-2 lg:grid-cols-1 gap-y-4 md:p-8 md:gap-4">
        <MenuItem v-for="data in menuData">
          <template #icon>
            <NuxtImg :src="`/images/menu/${data.icon}`" class="w-[24px]" />
          </template>
          <template #title> {{ data.title }} </template>
          <template #subtitle>
            {{ data.subtitle }}
          </template>
        </MenuItem>
      </div>
    </div>
  </div>
</template>
