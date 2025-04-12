<template>
    <div class="flex flex-col justify-center items-center">
        <!-- 导航栏 -->
        <div class="flex items-center w-fullitems-center w-full justify-evenly bg-primary-200">
            <ul class="flex gap-4">
                <li>
                    <UButton variant="ghost" color="secondary" class="rounded-2xl" to="/">简介</UButton>
                </li>
                <li>
                    <UButton variant="ghost" color="secondary" class="rounded-2xl" to="blogs">博客</UButton>
                </li>
            </ul>
            <UButton :icon="isDark ? 'i-lucide-moon' : 'i-lucide-sun'" color="secondary" variant="ghost"
                @click="isDark = !isDark" class="rounded-full" />
        </div>
        <UCard>
            博客内容
        </UCard>
    </div>
</template>

<script setup>
const colorMode = useColorMode()

const isDark = computed({
    get() {
        return colorMode.value === 'dark'
    },
    set() {
        colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
    }
})
</script>
