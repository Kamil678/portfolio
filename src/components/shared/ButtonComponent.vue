<template>
  <button class="basic-btn btn-large">{{ btnText }}</button>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps(['btnText'])
</script>

<style lang="scss">
.btn-large {
  font-size: 18px !important;
}
</style>
