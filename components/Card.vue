<script setup lang="ts">
const props = defineProps({
  data: Object,
});
</script>
<template>
  <div
    :class="`flex flex-col items-start justify-start gap-8 text-[#003e39] p-5 rounded-lg ${item.color} md:justify-center md:text-center md:p-10 border border-[#003e39] transition-all duration-300`"
    v-for="item in props.data"
  >
    <div class="flex flex-col items-center justify-center md:w-full">
      <div
        class="bg-[#F6F8FF] rounded-md ring-1 ring-[#003e39] shadow-[4px_4px_0px_0px_rgb(0,62,57)] w-[70px] h-[70px] flex flex-col items-center justify-center"
      >
        <NuxtImg :src="`/images/hero/${item.icon}`" class="w-[24px]" />
      </div>
    </div>
    <div class="flex flex-col md:w-full">
      <div class="text-[32px] font-semibold">
        {{ item.title }}
      </div>
      <div class="text-[14px]">{{ item.subtitle }}</div>
    </div>

    <div class="text-base md:ring-1 md:ring-[#003e39] md:p-3 md:rounded-lg">
      {{ item.description }}
    </div>

    <div class="flex items-center justify-center md:w-full">
      <ul
        class="list-image-[url('images/hero/hero3-numeric-icon.svg')] list-inside text-left"
      >
        <li v-for="li in item.numberings" class="py-1">{{ li }}</li>
      </ul>
    </div>

    <div class="flex flex-col w-full mt-5">
      <ButtonSecondary>{{ item.button }}</ButtonSecondary>
    </div>

    <div class="hidden w-full md:flex md:items-center md:justify-center">
        {{ item.footer }}
    </div>
  </div>
</template>
