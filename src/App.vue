<script setup lang="ts">
import { ref } from 'vue'
import { useQRCode } from '@vueuse/integrations/useQRCode'
// @ts-ignore
import { CreatedByMe } from 'gaute-web-components'

const text = ref('text-to-encode')
const qrcode = useQRCode(text, {
  quality: 1,
  margin: 2,
  width: 600,
})
</script>

<template>
  <main>
    <input v-model="text" type="text" maxlength="2300">
    <img :src="qrcode" alt="QR Code"/>
  </main>
  <footer>
    <created-by-me></created-by-me>
  </footer>
</template>

<style scoped>
main {
  display: grid;
  grid-template-rows: auto 1fr;
  gap: 1rem;
  justify-items: center;
  padding: 1rem;
}

input {
  font-size: 1.5rem;
}

img {
  border-radius: 5px;
  max-width: 75vw;
  max-height: 70vh;
}

footer {
  display: grid;
  place-items: center;
  padding: 1rem;
}
</style>
