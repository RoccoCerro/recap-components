<script >
import axios from "axios";
import AppCard from "./components/AppCard.vue";

export default{
  data() {
    return{
      cards:[]
    }
  },
  components:{
    AppCard
  },
  methods:{
    getRandomCard(){
      for(let i=0; i<=5; i++){
        axios.get('https://api.scryfall.com/cards/random').then((res)=>{

          const data = res.data
          
          const name=data.name;
          const image=data.image_uris.normal;

          this.cards.push({
            name,
            image
          })
        })

      }
    }
  },
  created(){
    this.getRandomCard()
  }
}
</script>

<template>
  <h1>Card Random</h1>
  <!-- <ul>
    <li v-for="card in cards">
      <div class="name">
        {{ card.name }}
      </div>
      <div class="image">
        <img .src="card.image" alt="">
      </div>
    </li>
  </ul> -->
  <!-- <p>{{ JSON.stringify(cards) }}</p> -->
  <div class="container">
    <ul class="row">
      <!-- <AppCard v-for="card in cards" :name="card.name" :image="card.image"/> -->
      <AppCard v-for="card in cards" :card="{name: card.name, image: card.image}"/>
    </ul>
  </div>
</template>

<style lang="scss">
@use './assets/scss/general.scss';
</style>
