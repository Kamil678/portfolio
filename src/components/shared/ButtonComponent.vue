<template>
  <button class="basic-btn">{{ btnText }}</button>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps(['btnText'])
</script>

<style lang="scss">
.basic-btn {
  padding: 15px 30px;
  background-color: $secondColor;
  font-size: 16px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  color: $textColor;
  transition: all 0.3s ease;

  &:hover {
    background-color: #1e40af;
  }
}
</style>
