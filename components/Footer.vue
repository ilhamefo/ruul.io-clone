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

const langs = ref([
  {
    id: "de",
    lang: "Deutsch",
    default: false,
    isActive: false,
    icon: "https://cdn.weglot.com/flags/circle/de.svg",
  },
  {
    id: "fe",
    lang: "Français",
    default: false,
    isActive: false,
    icon: "https://cdn.weglot.com/flags/circle/fr.svg",
  },
  {
    id: "es",
    lang: "Español",
    isActive: false,
    default: false,
    icon: "https://cdn.weglot.com/flags/circle/es.svg",
  },
  {
    id: "pl",
    lang: "Polski",
    icon: "https://cdn.weglot.com/flags/circle/pl.svg",
    isActive: false,
    default: false,
  },
  {
    id: "en",
    lang: "English",
    icon: "https://cdn.weglot.com/flags/circle/gb.svg",
    isActive: true,
    default: true,
  },
]);

const langState = ref(false);

const activeLang = computed(() => {
  return langs.value.find((lang) => {
    return lang.isActive;
  });
});

const inActiveLang = computed(() => {
  return langs.value.filter((lang) => {
    if (!lang.isActive) {
      return lang;
    }
  });
});

function setActiveLang(id) {
  langs.value.forEach((lang) => {
    if (id == lang.id) {
      lang.isActive = true;
    } else {
      lang.isActive = false;
    }
  });

  langs.value.sort((a, b) => {
    return a.lang - b.lang
  });
}
</script>
<template>
  <div
    class="flex flex-col items-center justify-center bg-[#003e39] text-[#cafdc6] py-[40px] px-[21.25px] md:py-[80px] lg:py-[100px] md:px-[40px]"
  >
    <div
      class="flex flex-col w-full gap-10 container-custom xl:flex-row border-b border-[#cafdc6]"
    >
      <div class="py-10 xl:p-0">
        <NuxtImg
          src="/images/6400030a281a43b4c0c93c4a_Logo3.svg"
          class="w-[84px]"
        >
        </NuxtImg>
      </div>

      <div class="grid grid-cols-2 gap-8 pb-14 lg:grid-cols-5">
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
    <div class="flex flex-col w-full gap-10 py-10 container-custom lg:flex-row lg:items-center lg:justify-center xl:justify-between">
      <div class="relative flex items-center justify-center">
        <ButtonPrimary
          class="text-[#003e39] py-2 flex items-center justify-center gap-2 bg-[#cafdc6] px-10"
          @click="langState = !langState"
        >
          <NuxtImg :src="activeLang.icon" class="w-[18px]"></NuxtImg>
          <span class="text-base font-semibold">{{ activeLang.lang }}</span>
          <NuxtImg
            src="/images/chevron.svg"
            format="webp"
            class="transition-none duration-300 -rotate-90 reverse-spin"
            :class="[langState ? 'rotate-180' : '-rotate-90']"
          ></NuxtImg>
        </ButtonPrimary>

        <div
          class="bg-[#cafdc6] absolute bottom-12 text-[#003e39] py-2 flex items-start justify-start flex-col gap-3 rounded-lg"
          v-if="langState"
        >
          <button
            class="flex items-start justify-start w-full gap-2 px-10"
            v-for="lang in inActiveLang"
            @click="setActiveLang(lang.id)"
          >
            <NuxtImg :src="lang.icon" class="w-[18px]"></NuxtImg>
            {{ lang.lang }}
          </button>
        </div>
      </div>
      <div class="flex items-center justify-center gap-3">
        <div class="">Copyright ©2023 ruul.io</div>
        <div class="">Privacy Policy</div>
        <div class="">Terms Of Use</div>
        <div class="">DSAR</div>
      </div>
      <div class="">
        <FooterIcons />
      </div>
    </div>
  </div>
</template>
