<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <img :src="imagem" alt="Card image">
      <p class="card-text">{{ text.substring(0, 200) }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: { type: String, required: true },
    text: { type: String, required: true },
    imagem: { type: String, required: true }
  }
}
</script>

<style scoped>
.card { width: 900px; padding: 10px; display: flex; justify-content: center; }
.card-title{ font-size: 1.5rem; font-weight: bold; display: flex; justify-content: center }
.card-text{ font-size: 20px; }
</style>
