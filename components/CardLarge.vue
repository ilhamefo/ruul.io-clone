<script setup lang="ts">
const props = defineProps({
  data: Object,
});
</script>
<template>
  <div
    :class="[
      item.type !== 'content'
        ? `${item.background} bg-no-repeat bg-center bg-cover hidden lg:flex flex-col items-start justify-start gap-8 text-[#003e39] p-6 rounded-lg ${item.color} md:p-10 border border-[#003e39] transition-all duration-300`
        : `flex flex-col items-start justify-start gap-8 text-[#003e39] p-6 rounded-lg ${item.color} md:p-10 border border-[#003e39] transition-all duration-300`,
    ]"
    v-for="item in props.data"
  >
    <div
      class="flex flex-col md:w-full"
      :class="[item.type !== 'content' ? 'hidden' : '']"
    >
      <div
        class="bg-[#CAFDC6] rounded-md ring-1 ring-[#003e39] shadow-[4px_4px_0px_0px_rgb(0,62,57)] w-[70px] h-[70px] flex flex-col items-center justify-center"
      >
        <NuxtImg
          :src="`/images/hero/${item.icon}`"
          class="w-[24px] md:w-[38px]"
        />
      </div>
    </div>

    <div
      class="flex flex-col md:w-full"
      :class="[item.type !== 'content' ? 'hidden' : '']"
    >
      <div class="text-[32px] font-semibold md:text-5xl">
        {{ item.title }}
      </div>
    </div>

    <div class="text-lg" :class="[item.type !== 'content' ? 'hidden' : '']">
      {{ item.description }}
    </div>

    <div
      class="flex md:w-full"
      :class="[item.type !== 'content' ? 'hidden' : '']"
    >
      <ul
        class="list-image-[url('images/hero/hero3-numeric-icon.svg')] list-inside text-left"
      >
        <li v-for="li in item.numberings" class="py-1">{{ li }}</li>
      </ul>
    </div>

    <div
      class="flex flex-col w-full mt-5"
      :class="[item.type !== 'content' ? 'hidden' : '']"
    >
      <ButtonSecondary class="flex items-center justify-center gap-0 md:gap-2">
        <span class="">
          {{ item.button }}
        </span>
        <span class="w-[24px] h-[24px] hidden md:flex">
          <LazyIconsBtnArrow />
        </span>
      </ButtonSecondary>
    </div>
  </div>
</template>
