<template>
  <div class="card-collection">
    <GameCard
      v-for="card in cards"
      :key="card.id"
      :name="card.name"
      :type="card.type"
      :strength="card.strength"
      :description="card.description"
      :image="card.image"
      :faceDown="card.faceDown"
    />
  </div>
</template>

<script>
import GameCard from './card/card.vue';

export default {
  components: {
    GameCard
  },
  data() {
  return {
    cards: [
      {
        id: 1,
        name: 'Геральт из Ривии',
        type: 'Герой',
        strength: 10,
        description: 'Опытный ведьмак, непревзойденно владеющий мечом. уничтожьте вражеский отряд с силой не менее 9 ед.',
        image: "/card/images/geralt_of_rivia.jpeg",
        faceDown: false
      },
      {
        id: 2,
        name: 'Трисс Меригольд',
        type: 'Маг',
        strength: 7,
        description: 'Могущественная волшебница и близкая подруга Геральта. Вскройте случайный отряд из вашей колоды и нанесите вражескому отряду урон, равный силе вскрытого отряда.',
        image: '/path/to/triss-image.jpg',
        faceDown: false
      },
      {
        id: 3,
        name: 'Йеннифэр из Венгерберга',
        type: 'Маг',
        strength: 8,
        description: 'Хитрая волшебница с огромными магическими навыками. Выберите одну карту из вашего отбоя (не героя и не специальную карту и сыграйте ее немедленно).',
        image: '/path/to/yennefer-image.jpg',
        faceDown: false
      },
      {
        id: 4,
        name: 'Данделион',
        type: 'Помощник',
        strength: 2,
        description: 'Бард и верный друг Геральта. Удваивает силу всех карт юнитов в этом ряду. Ограничено 1 в ряду',
        image: '/path/to/dandelion-image.jpg',
        faceDown: false
      },
      {
        id: 5,
        name: 'Весемир',
        type: 'Воин',
        strength: 6,
        description: 'Старший ведьмак и наставник Геральта. Уысильте всех ведьмаков в вашем распоряжении на 1 ед.',
        image: '/path/to/vesemir-image.jpg',
        faceDown: false
      },
      {
        id: 6,
        name: 'Золтан Хивай',
        type: 'Краснолюд',
        strength: 5,
        description: 'Гном с острым языком и еще более острым мечом. Усильте смежных краснолюдов на 2 ед.',
        image: '/path/to/zoltan-image.jpg',
        faceDown: false
      },
      {
        id: 7,
        name: 'Цири',
        type: 'Герой',
        strength: 9,
        description: 'Приемная дочь Геральта, обладающая таинственными способностями. если в вашей стартовой колоде нет карт со стоимостью найма 10 ед. или выше, добавьте стойкость, щит и покров.',
        image: '/path/to/ciri-image.jpg',
        faceDown: false
      },
      {
        id: 8,
        name: 'Роше',
        type: 'Воин',
        strength: 6,
        description: 'Дрянь человек, но патриот. сыграйте 2 верхние карты из вашей колоды.',
        image: '/path/to/roche-image.jpg',
        faceDown: false
      },
      {
        id: 9,
        name: 'Эмгыр вар Эмрейс',
        type: 'Лидер',
        strength: 10,
        description: 'Император Нильфгаарда и один из врагов Геральта. Если в колоде есть карта Ливень, то она будет сыграна немедленно.',
        image: '/path/to/emhyr-image.jpg',
        faceDown: false
      },
      {
        id: 10,
        name: 'Имлерих',
        type: 'Монстр',
        strength: 8,
        description: 'Жестокий генерал Дикой Охоты. Возьмите карту, затем сбросьте карту. Если сброшенная карта — это отряд, усильте эту карту на его силу.',
        image: '/path/to/imlerith-image.jpg',
        faceDown: false
      },
      {
        id: 11,
        name: 'Caranthir',
        type: 'Mage',
        strength: 7,
        description: 'A powerful mage serving the Wild Hunt.',
        image: '/path/to/caranthir-image.jpg',
        faceDown: false
      },
      {
        id: 12,
        name: 'Eredin',
        type: 'Monster',
        strength: 9,
        description: 'The king of the Wild Hunt, a ruthless leader.',
        image: '/path/to/eredin-image.jpg',
        faceDown: false
      },
      {
        id: 13,
        name: 'Lambert',
        type: 'Warrior',
        strength: 5,
        description: 'A witcher with a quick wit and quick temper.',
        image: '/path/to/lambert-image.jpg',
        faceDown: false
      },
      {
        id: 14,
        name: 'Eskel',
        type: 'Warrior',
        strength: 6,
        description: 'A calm and skilled witcher, and Geralt’s friend.',
        image: '/path/to/eskel-image.jpg',
        faceDown: false
      },
      {
        id: 15,
        name: 'Kayran',
        type: 'Monster',
        strength: 7,
        description: 'A monstrous creature that lurks in the waters.',
        image: '/path/to/kayran-image.jpg',
        faceDown: false
      },
      {
        id: 16,
        name: 'Philippa Eilhart',
        type: 'Mage',
        strength: 7,
        description: 'A ruthless sorceress and political manipulator.',
        image: '/path/to/philippa-image.jpg',
        faceDown: false
      },
      {
        id: 17,
        name: 'Dettlaff',
        type: 'Monster',
        strength: 10,
        description: 'A higher vampire of fearsome power.',
        image: '/path/to/dettlaff-image.jpg',
        faceDown: false
      },
      {
        id: 18,
        name: 'Letho of Gulet',
        type: 'Assassin',
        strength: 8,
        description: 'A witcher skilled in the art of killing.',
        image: '/path/to/letho-image.jpg',
        faceDown: false
      },
      {
        id: 19,
        name: 'Regis',
        type: 'Vampire',
        strength: 6,
        description: 'A reformed vampire and close friend of Geralt.',
        image: '/path/to/regis-image.jpg',
        faceDown: false
      },
      {
        id: 20,
        name: 'Saskia',
        type: 'Hero',
        strength: 9,
        description: 'A brave warrior and leader of the free people.',
        image: '/path/to/saskia-image.jpg',
        faceDown: false
      }
    ]
  };
}

};
</script>

<style scoped>
.card-collection {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 10px;
}
</style>
