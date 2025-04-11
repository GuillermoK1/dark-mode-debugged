<template>
      <ClientOnly>
        <UButton
        class="mx-2 w-10 h-10 ml-8"
        variant="ghost"
        color="black"
        :icon="colorMode.value === 'dark' ? 'i-heroicons-moon' : 'i-heroicons-sun'"
        @click="toggleColorMode"
      />
      </ClientOnly>
<template>

<script setup lang='ts'>
const colorMode = useColorMode()

// Initialize color mode preference
onMounted(() => {
  // Set initial color mode based on system preference
  if (!colorMode.preference) {
    colorMode.preference = window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light'
  }
})

const toggleColorMode = () => {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
}
<script>
