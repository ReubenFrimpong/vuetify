<template>
  <div class="px-2">
    <div class="ps-1 mb-3">
      <v-label :text="t('theme')" class="mb-2 font-weight-medium" />

      <v-messages :messages="t('theme-message')" active />
    </div>

    <theme-option />

    <v-divider class="my-3" />

    <div class="ps-1 mb-3">
      <v-label :text="t('general')" class="mb-2 font-weight-medium" />

      <v-messages :messages="t('general-message')" active />
    </div>

    <template v-if="user.dev">
      <ad-option />
    </template>

    <code-option />

    <api-option />

    <slash-search-option />

    <sync-option />
  </div>
</template>

<script setup>
  // Components
  import AdOption from '@/components/app/settings/options/AdOption.vue'
  import ApiOption from '@/components/app/settings/options/ApiOption.vue'
  import CodeOption from '@/components/app/settings/options/CodeOption.vue'
  import SyncOption from '@/components/app/settings/options/SyncOption.vue'
  import SlashSearchOption from '@/components/app/settings/options/SlashSearchOption.vue'
  import ThemeOption from '@/components/app/settings/options/ThemeOption.vue'

  // Composables
  import { useI18n } from 'vue-i18n'
  import { useUserStore } from '@/store/user'

  const { t } = useI18n()
  const user = useUserStore()
</script>
