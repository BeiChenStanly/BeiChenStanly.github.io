<template>
  <div>
    <!-- 导航栏 -->
    <div class="flex items-center w-full justify-evenly bg-primary-300">
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
    <!-- 内容 -->
    <div class="flex items-center justify-around w-full flex-col">
      <UAvatar src="touxiangnew.jpg" size="3xl" />
      <strong>BeiChenStanly</strong>
    </div>
  </div>
</template>

<script setup lang="ts">
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
