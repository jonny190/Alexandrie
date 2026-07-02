<script setup lang="ts">
// Link-preview card for public documents, rendered to a PNG by nuxt-og-image (satori).
// Keep the markup to satori's supported CSS subset: every element with >1 child sets
// display:flex, no `gap`, explicit sizes, inline styles.
withDefaults(
  defineProps<{
    title?: string;
    description?: string;
    site?: string;
  }>(),
  {
    title: 'Untitled document',
    description: '',
    site: 'Alexandrie',
  },
);
</script>

<template>
  <div
    style="
      display: flex;
      flex-direction: column;
      width: 100%;
      height: 100%;
      padding: 80px;
      background-color: #0b1220;
      background-image: linear-gradient(135deg, #0b1220 0%, #131c33 100%);
      color: #ffffff;
    "
  >
    <!-- Brand row -->
    <div style="display: flex; align-items: center;">
      <div
        style="
          display: flex;
          width: 56px;
          height: 56px;
          border-radius: 14px;
          background-color: #3956e7;
        "
      />
      <div style="margin-left: 22px; font-size: 36px; font-weight: 600; color: #e8ecf8;">{{ site }}</div>
    </div>

    <!-- Title + description, pushed to the lower half -->
    <div style="display: flex; flex-direction: column; margin-top: auto;">
      <div style="display: flex; font-size: 66px; font-weight: 700; line-height: 1.12; color: #ffffff;">
        {{ title }}
      </div>
      <div v-if="description" style="display: flex; margin-top: 28px; font-size: 30px; line-height: 1.35; color: #9fb0d0;">
        {{ description }}
      </div>
    </div>

    <!-- Accent underline -->
    <div style="display: flex; margin-top: 44px; width: 140px; height: 8px; border-radius: 4px; background-color: #3956e7;" />
  </div>
</template>
