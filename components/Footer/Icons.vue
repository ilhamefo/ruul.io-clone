<script setup>
const icons = ref([
    {
        icon: "/images/social_media/fb.svg",
        link: "https://fb.me/ilhamefo"
    },
    {
        icon: "/images/social_media/ig.svg",
        link: "https://instagram.com/ilhamefo_"
    },
    {
        icon: "/images/social_media/twitter.svg",
        link: "https://twitter.com/ilhamefo"
    },
    {
        icon: "/images/social_media/linkedin.svg",
        link: "https://www.linkedin.com/in/ilham-efo-hernanda/"
    },
])
</script>
<template>
    <div class="flex items-center justify-center gap-5 ">
        <a :href="icon.link" target="_blank" class="bg-[#cafdc6] w-fit rounded-full p-2 fill-red-500" v-for="icon in icons">
            <NuxtImg :src="icon.icon"></NuxtImg>
        </a>
    </div>
</template>