<template>
  <button class="flex items-start justify-start gap-5">
    <div
      class="bg-[#C9FEC6] rounded-full p-3 ring-1 ring-[#003e39] shadow-[4px_4px_0px_0px_rgb(0,62,57)]"
    >
      <slot name="icon">
        <NuxtImg src="/images/menu/icon-1.svg" class="w-[24px]" />
      </slot>
    </div>
    <div class="flex flex-col items-start justify-start py-2">
      <div class="text-xl font-semibold text-left">
        <slot name="title"> Global Invoicing </slot>
      </div>
      <div class="text-base font-normal text-left">
        <slot name="subtitle"> Invoice globally without a legal entity. </slot>
      </div>
    </div>
  </button>
</template>
