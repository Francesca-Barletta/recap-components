<script>
import axios from 'axios';
import AppCard from './components/AppCard.vue'
export default {
  components: {
    AppCard
  },
  data(){
    return{
      cards: [],
    }
  },
  methods: {
    fetchCard() {
      for (let i = 0; i < 5; i++) {
        axios.get('https://api.scryfall.com/cards/random')
          .then((res) => {
            // console.log(res);
            const data = res.data;
            const name = data.name;
            // console.log(name);
            const image = data.image_uris.normal;
            // console.log(image);
            this.cards.push({name, image});
          })
      }
      console.log(this.cards)
    }
  },
  mounted(){
    this.fetchCard();
  }
}
</script>

<template>
  <h1>Magic Card Generator</h1>
  <ul>
    <li v-for="card in cards">
      <AppCard :card="card"/>
    </li>
  </ul>

</template>

<style lang="scss" scoped>

</style>
