<script setup lang="ts">
import { ref } from 'vue'
import { useQRCode } from '@vueuse/integrations/useQRCode'

const text = ref('https://gaute.dev')
const qrcode = useQRCode(text, {
  quality: 1,
  margin: 2,
  width: 600,
})
</script>

<template>
  <input v-model="text" type="text" maxlength="2300">
  <img :src="qrcode" alt="QR Code" />
</template>

<style scoped>
input {
  font-size: 1.5rem;
}

img {
  border-radius: 5px;
  max-width: 75vw;
  max-height: 70vh;
}
</style>
