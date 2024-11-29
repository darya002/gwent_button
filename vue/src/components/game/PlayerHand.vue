<template>
  <div class="hand-container">
    <div :class="handClass">
      <div
        class="hand__card"
        v-for="(card, index) in cards"
        :key="index"
        :style="applyTransform(index)"
        @mouseover="handleMouseOver(index)"
        @mouseleave="handleMouseLeave"
      >
        <GameCard
          :key="index"
          :type="card.type"
          :score="card.score"
          :image-uri="card.image"
          :face-down="opponent"
          :enlarged="!opponent"
          :is-opponent="opponent"
          :index="index"
          @onDrop="(params) => $emit('onCardDrop', params)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import GameCard from "@/components/game/GameCard.vue";
import { mapGetters } from "vuex";

export default {
  name: 'PlayerHand',
  components: { GameCard },
  emits: ['onCardDrop'],
  props: {
    opponent: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      hoveredIndex: null,
    };
  },
  computed: {
    ...mapGetters('gameEngine', [
      'getGameEngine',
    ]),
    cards() {
      return this.opponent ?
          this.getGameEngine.opponent.cards :
          this.getGameEngine.player.cards
    },
    handClass() {
      return this.opponent ? "hand-opponent" : "hand-player";
    },
  },
  methods: {
    applyTransform(index) {
  const angle = (index - (this.cards.length - 1) / 2) * 10; 
  const isHovered = this.hoveredIndex === index;
  return {
    transform: `rotate(${angle}deg)`,  // Убираем translateY, чтобы не было лишних сдвигов
    transition: "transform 0.2s ease-out",
    zIndex: isHovered ? 100 : index,
  };
},

    handleMouseOver(index) {
      this.hoveredIndex = index;
    },
    handleMouseLeave() {
      this.hoveredIndex = null;
    },
  },
};
</script>

<style scoped lang="less">
.hand {
  display: flex;
  position: absolute;
  z-index: 666;
  width: 80vw;
  margin: auto;
  justify-content: center;
  perspective: 1000px;

  &__card {
    width: 150px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute; 
    font-size: 18px;
    color: black;
    transform-origin: bottom center;
  }

  &-player:extend(.hand) {
    bottom: -20px;
    height: 20vh;
  }

  &-opponent:extend(.hand) {
    top: -25px;
    height: 15vh;
  }
}

.hand-container {
  display: flex;
  justify-content: center;
}
</style>
