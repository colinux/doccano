<template>
  <v-tooltip bottom>
    <template v-slot:activator="{ on }">
      <button-review-icon
        :is-reviewd="isReviewd"
        :tooltip-activator="on"
        @click:review="$emit('click:review')"
       />
    </template>
    <span v-if="isReviewd">{{ $t('annotation.checkedTooltip') }}</span>
    <span v-else>{{ $t('annotation.notCheckedTooltip') }}</span>
  </v-tooltip>
</template>

<script lang="ts">
import Vue from 'vue'

import ButtonReviewIcon from './ButtonReviewIcon.vue'
export default Vue.extend({
  components: {
    ButtonReviewIcon,
  },
  props: {
    isReviewd: {
      type: Boolean,
      default: false,
      required: true
    }
  }
})
</script>
