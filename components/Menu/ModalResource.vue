<script setup>
const menuData2 = ref([
  {
    title: "About us",
    subtitle: "Read about our vision for shaping the future of work.",
  },
  {
    title: "Ruul Blog",
    subtitle:
      "Keep up with the latest news and trends in the global work landscape.",
  },
  {
    title: "Support",
    subtitle: "Get more detailed information about Ruul products.",
  },
]);

const menuData = ref([
  {
    icon: "icon-12.svg",
    title: "Ruul Community",
    subtitle: "Share, learn and grow.",
  },
  {
    icon: "icon-13.svg",
    title: "Help Center",
    subtitle: "Contact us at info@ruul.io",
  },
]);

const menuData3 = ref([
  {
    image: "img-1.png",
    title: "How to invoice as a freelancer: A brief guide",
    subtitle: "Learn More.",
  },
  {
    image: "img-2.png",
    title:
      "Talent Talks #4: Meet photographer & cinematographer Vasilis Barahanos",
    subtitle: "Learn More.",
  },
  {
    image: "img-3.png",
    title: "Ruulmates on the mic #4: Thriving in remote work with Peter Benei",
    subtitle: "Learn More.",
  },
]);
</script>
<template>
  <div
    class="w-full top-14 border rounded-lg border-[#003e39] shadow-[0_2.8px_2.2px_rgba(0,_0,_0,_0.034),_0_6.7px_5.3px_rgba(0,_0,_0,_0.048),_0_12.5px_10px_rgba(0,_0,_0,_0.06),_0_22.3px_17.9px_rgba(0,_0,_0,_0.072),_0_41.8px_33.4px_rgba(0,_0,_0,_0.086),_0_100px_80px_rgba(0,_0,_0,_0.12)] overflow-hidden"
  >
    <div class="flex flex-col gap-5 lg:gap-0 bg-[#F6F8FF]">
      <div class="flex items-start justify-start">
        <div
          class="hidden lg:grid grid-cols-1 md:grid-cols-2 lg:grid-cols-1 gap-4 p-3 md:p-5 lg:p-10 border-r border-[#003e39] flex-grow"
        >
          <!-- Loop -->
          <div
            class="flex items-start justify-start gap-5"
            v-for="data in menuData3"
          >
            <div class="grid grid-cols-[min-content_1fr] gap-5">
              <div
                class="w-[175px] h-[140px] bg-[#397] rounded-md border border-[#003e39] flex items-center justify-center"
              >
                <NuxtImg
                  :src="`/images/${data.image}`"
                  class="object-cover"
                  :format="'webp'"
                ></NuxtImg>
              </div>
              <button class="flex flex-col items-start justify-start gap-2 py-2">
                <div class="text-base font-semibold text-left">
                  {{ data.title }}
                </div>
                <div class="flex items-center justify-start gap-1 text-base font-normal text-left">
                  <span class="">{{ data.subtitle }}</span>
                  <span class="">
                    <NuxtImg src="/images/arrow-up-right.svg" class="h-[16px] w-[16px] fill-[#397]"></NuxtImg>
                  </span>
                </div>
              </button>
            </div>
          </div>
          <!-- End loop -->
        </div>

        <div
          class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-1 gap-4 bg-[#F6F8FF] p-3 md:p-5 lg:p-10 flex-grow-0 w-fit"
        >
          <!-- Loop -->
          <div
            class="flex items-start justify-start gap-5"
            v-for="data in menuData2"
          >
            <button class="flex flex-col items-start justify-start py-2">
              <div class="text-xl font-semibold text-left">
                {{ data.title }}
              </div>
              <div class="text-base font-normal text-left">
                {{ data.subtitle }}
              </div>
            </button>
          </div>
          <!-- End loop -->
        </div>
      </div>
      <div
        class="grid grid-cols-1 md:grid-cols-2 gap-4 bg-[#FEEECA] border-t border-[#003e39] p-3 md:p-5 lg:p-10"
      >
        <!-- Loop -->
        <div
          class="flex items-start justify-start gap-5"
          v-for="data in menuData"
        >
          <div
            class="bg-[#C9FEC6] rounded-full p-3 ring-1 ring-[#003e39] shadow-[4px_4px_0px_0px_rgb(0,62,57)]"
          >
            <NuxtImg :src="`/images/menu/${data.icon}`" class="w-[24px]" />
          </div>
          <div class="flex flex-col items-start justify-start py-2">
            <div class="text-xl font-semibold text-left">{{ data.title }}</div>
            <div class="text-base font-normal text-left">
              {{ data.subtitle }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
