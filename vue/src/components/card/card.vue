<template>
  <div class="game-card" :class="{ faceDown }">
    <img v-if="!faceDown" :src="image" :alt="name" class="card-image" />
    <div v-if="!faceDown" class="card-content">
      <h3 class="card-title">{{ name }}</h3>
      <p class="card-type">Type: {{ type }}</p>
      <p class="card-strength">Strength: {{ strength }}</p>
      <p class="card-description">{{ description }}</p>
    </div>
    <div v-else>
      <p>Card is face down</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GameCard',
  props: {
    name: {
      type: String,
      required: true
    },
    type: {
      type: String,
      required: true
    },
    strength: {
      type: Number,
      required: true
    },
    description: {
      type: String,
      required: false,
      default: ''
    },
    image: {
      type: Image,
      required: true
    },
    faceDown: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cinzel+Decorative&family=Cardo&display=swap');

.game-card {
  width: 150px;
  height: 250px;
  border: 1px solid black;
  text-align: center;
  transition: transform 0.5s, background-color 0.3s, box-shadow 0.3s;
  position: relative;
  background-color: antiquewhite;
  border-radius: 5%;
}

.card-image {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.card-content {
  padding: 10px;
}

.card-title {
  font-family: 'Cinzel Decorative', serif;
  font-size: 18px;
  margin-bottom: 5px;
  color: #472828;
}

.card-type, .card-strength {
  font-family: 'Cardo', serif;
  font-size: 14px;
  color: #321c1c;
}

.card-description {
  font-family: 'Cardo', serif;
  font-size: 12px;
  color: #250303;
}

.game-card:hover {
  box-shadow: 0 0 15px 5px rgba(69, 56, 47, 0.8);
}

.game-card.faceDown {
  background-color: gray;
}
</style>
