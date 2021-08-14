<template>
  <v-btn
    icon
    @click="$emit('click:review')"
    v-on="tooltipActivator"
  >
    <v-icon v-if="isReviewd">
      mdi-check
    </v-icon>
    <v-icon v-else>
      mdi-close
    </v-icon>
  </v-btn>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    isReviewd: {
      type: Boolean,
      default: false,
      required: true
    },

    tooltipActivator: {
      type: Object,
      default: undefined
    }
  }
})
</script>
