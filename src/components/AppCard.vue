<template>
  <li class="col">
    <div class="name">
      {{ card.name }}
    </div>
    <div class="image">
      <img :src="card.image" alt="" />
    </div>   
  </li> 
</template> 

<script>
export default {
  props: {
    // name: "string",
    // image: "string",
    card: Object
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/scss/general.scss";

li {
  padding: 0 10px;
}

.name {
  font-size: large;
  font-weight: bold;
  padding: 10px 0;
  color: rgba(0, 0, 0, 0.445);
}

@media (max-width:500px) {
  .name{
    font-size: 8px;
  }
}
</style>
