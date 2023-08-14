<script setup>
const menuData = ref([
  {
    icon: "icon-5.svg",
    title: "AOR",
    subtitle: "Work with off-payroll talents globally in compliance.",
  },
  {
    icon: "icon-6.svg",
    title: "Payments",
    subtitle: "Make safe and secure payments without banking fees.",
  },
  {
    icon: "icon-7.svg",
    title: "Talent Management",
    subtitle: "Manage your talents on a single dashboard.",
  },
]);

const heroData = ref({
  image: "icon-15.svg",
  title: "Ruul For Businesses",
  subtitle:
    "Effortlessly manage and pay your workforce, ensuring compliance with agility.",
  button: "See all talent business",
});

</script>
<template>
  <div
    class="bg-[#F6F8FF] w-full top-14 border rounded-lg border-[#003e39] shadow-[0_2.8px_2.2px_rgba(0,_0,_0,_0.034),_0_6.7px_5.3px_rgba(0,_0,_0,_0.048),_0_12.5px_10px_rgba(0,_0,_0,_0.06),_0_22.3px_17.9px_rgba(0,_0,_0,_0.072),_0_41.8px_33.4px_rgba(0,_0,_0,_0.086),_0_100px_80px_rgba(0,_0,_0,_0.12)] overflow-hidden"
  >
    <div class="flex flex-col md:gap-y-5 lg:flex-row">
      <div class="md:bg-[#FFC1AE] flex flex-col gap-y-5 p-4 md:p-8 lg:border-r lg:border-[#003e39]">
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
