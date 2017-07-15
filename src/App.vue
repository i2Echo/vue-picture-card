<template>
  <div id="app">
    <div class="wrapper">
      <card
      :src=" './static/images/pic1.jpg' "
      :title=" 'Title' "
      :discription=" 'Discription' "
      :category=" 'Material Design' "
      :width=" 300 "
      ></card>
      <card
      :src=" './static/images/pic1.jpg' "
      :title=" 'Title1' "
      :discription=" 'Discription1' "
      ></card>
      <card
      :src=" './static/images/pic1.jpg' "
      :title=" 'Title2' "
      :discription=" 'Discription2' "
      ></card>
      <card
      :src=" './static/images/pic1.jpg' "
      :title=" 'Title3' "
      :discription=" 'Discription3' "
      ></card>
    </div>
  </div>
</template>

<script>
import Card from './components/Card'

export default {
  name: 'app',
  components: {
    Card
  }
}
</script>

<style>

#app {
  /* font-family: 'Avenir', Helvetica, Arial, sans-serif; */
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  /* background-color: #eee; */
}
@media (min-width: 501px){
  .wrapper {
    width: 90%;
    margin: 0 auto;
  }
}
.wrapper {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  padding-top: 60px;
}

</style>
