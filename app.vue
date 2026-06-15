<template>
  <div>
    <NConfigProvider>
      <NDialogProvider>
        <ClientOnly>
          <NuxtPage />
        </ClientOnly>
      </NDialogProvider>
    </NConfigProvider>
  </div>
</template>

<script setup>
import { NConfigProvider, NDialogProvider } from 'naive-ui'
</script>
