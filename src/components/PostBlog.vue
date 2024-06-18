<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <img :src="imagem" alt="Card image" class="card-image">
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
.card {
  width: 100%;
  box-sizing: border-box; 
  margin: 0 auto; 
  max-width: 900px;
  padding: 10px;
}

.card-body {
  text-align: center;
}

.card-title {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: center; 
}

.card-image {
  max-width: 100%;
  height: auto;
  display: block; 
  margin: 0 auto 15px; 
  
}

.card-text {
  font-size: 20px;
  text-align: left; 
}
</style>
