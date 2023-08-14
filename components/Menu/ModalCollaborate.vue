<script setup>
const menuData = ref([
  {
    icon: "icon-8.svg",
    title: "Partners",
    subtitle:
      "Join our partner ecosystem, elevate your marketing & product impact.",
  },
  {
    icon: "icon-9.svg",
    title: "Affiliate Program",
    subtitle: "Help us revolutionize work dynamics, and generate income.",
  },
  {
    icon: "icon-10.svg",
    title: "HR Partner Program",
    subtitle: "Hire at every corner, earn as an HR partner.",
  },
  {
    icon: "icon-11.svg",
    title: "Ruul Community",
    subtitle: "Connect with fellow solo professionals, empower your career.",
  },
]);

const heroData = ref({
  image: "icon-14.svg",
  title: "Partner Programs",
  subtitle:
    "There are many ways to partner with us. Find the right fit for you and your business.",
  button: "Discover Partner Programs",
});
</script>
<template>
  <div
    class="bg-[#F6F8FF] w-full top-14 border rounded-lg border-[#003e39] shadow-[0_2.8px_2.2px_rgba(0,_0,_0,_0.034),_0_6.7px_5.3px_rgba(0,_0,_0,_0.048),_0_12.5px_10px_rgba(0,_0,_0,_0.06),_0_22.3px_17.9px_rgba(0,_0,_0,_0.072),_0_41.8px_33.4px_rgba(0,_0,_0,_0.086),_0_100px_80px_rgba(0,_0,_0,_0.12)] overflow-hidden"
  >
    <div class="flex flex-col md:gap-y-5 lg:flex-row">
      <div
        class="md:bg-[#FEEECA] flex flex-col gap-y-5 p-4 md:p-8 lg:border-r lg:border-[#003e39]"
      >
        <div class="text-[#003e39] text-4xl font-semibold hidden md:flex">
          {{ heroData.title }}
        </div>
        <div class="text-[#003e39] hidden md:flex">
          {{ heroData.subtitle }}
        </div>

        <div class="hidden rounded-lg overflow-clip lg:flex">
          <NuxtImg :src="`/images/menu/${heroData.image}`" />
        </div>
        <ButtonSecondary class="md:w-fit lg:w-full">
          <span class="font-medium text-white">{{ heroData.button }}</span>
        </ButtonSecondary>
      </div>

      <div
        class="grid grid-cols-1 p-4 md:grid-cols-2 lg:grid-cols-1 gap-y-4 md:p-8"
      >
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
