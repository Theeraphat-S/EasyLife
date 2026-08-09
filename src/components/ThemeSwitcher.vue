<script setup lang="ts">
import { useThemeMode } from "@/composables/useThemeMode";

const { mode, toggleMode } = useThemeMode();
</script>

<template>
  <VBtn
    icon
    variant="text"
    density="comfortable"
    :aria-label="`theme (${mode})`"
    :title="$t('common.theme.title', { mode: $t(`common.theme.${mode}`) })"
    @click="toggleMode"
  >
    <VIcon
      :icon="
        mode === 'dark'
          ? 'mdi-weather-night'
          : mode === 'light'
            ? 'mdi-weather-sunny'
            : 'mdi-desktop-tower-monitor'
      "
      size="20"
    />
  </VBtn>
</template>
