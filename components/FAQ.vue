<script setup lang="ts">
const faqs = ref([
  {
    id: <number>1,
    isActive: false,
    title: "What does Ruul do?",
    description:
      "Ruul enables solo talents and businesses to work compliantly and flexibly with custom worktech solutions tailored for the new work landscape. The set of solutions offered include globally recognized invoices, cross-currency payments, global employment, and tax assistance.",
  },
  {
    id: <number>2,
    isActive: false,
    title: "What does Ruul do?",
    description:
      "Ruul enables solo talents and businesses to work compliantly and flexibly with custom worktech solutions tailored for the new work landscape. The set of solutions offered include globally recognized invoices, cross-currency payments, global employment, and tax assistance.",
  },
  {
    id: <number>3,
    isActive: false,
    title: "What does Ruul do?",
    description:
      "Ruul enables solo talents and businesses to work compliantly and flexibly with custom worktech solutions tailored for the new work landscape. The set of solutions offered include globally recognized invoices, cross-currency payments, global employment, and tax assistance.",
  },
  {
    id: <number>4,
    isActive: false,
    title: "What does Ruul do?",
    description:
      "Ruul enables solo talents and businesses to work compliantly and flexibly with custom worktech solutions tailored for the new work landscape. The set of solutions offered include globally recognized invoices, cross-currency payments, global employment, and tax assistance.",
  },
]);

function toggleFAQ(faqId: number) {
  faqs.value.forEach((faq) => {
    if (faq.id === faqId) {
      faq.isActive = !faq.isActive;
    } else {
      faq.isActive = false;
    }
  });
}
</script>
<template>
  <div class="grid grid-cols-1 gap-3 md:gap-5">
    <button
      @click="toggleFAQ(faq.id)"
      class="flex flex-col items-stretch p-3 rounded-lg border border-[#003e39] gap-3 text-lg font-medium md:p-8 md:text-lg md:font-semibold"
      v-for="faq in faqs"
      :key="faq.id"
    >
      <div class="flex items-center justify-between">
        <div class="">{{ faq.title }}</div>
        <div class="bg-[#003e39] p-2 rounded-md">
          <NuxtImg
            src="/images/chevron-secondary.svg"
            format="webp"
            class="transition-all duration-300"
            :class="[faq.isActive ? '-rotate-180' : '']"
          >
          </NuxtImg>
        </div>
      </div>

      <div class="flex items-start pr-5 text-left transition-all duration-300" v-if="faq.isActive">
        {{ faq.description }}
      </div>
    </button>
  </div>
</template>
