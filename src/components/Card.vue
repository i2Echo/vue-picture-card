<template>
  <div class="card" v-bind:style="styleObject">
    <a :href="url">
      <div class="bg" v-bind:style="{ backgroundImage: getBackgroundImage }"></div>
    </a>
    <div class="discription">
      <div class="row">
        <div class="title long-text">{{ title }}</div>
        <div class="category long-text" v-if="this.category">{{ category }}</div>
        <div class="column-flex more">
          <div class="long-text">{{ discription }}</div>
          <div class="fa fa-share"></div>
        </div>
        
      </div>
    </div>    
   
  </div>
</template>

<script>
export default {
  name: 'card',
  props: {
    width: {
      type: Number,
      defualt: 250
    },
    url: {
      type: String,
      defualt: '#'
    },
    src: {
      type: String,
      require: true
    },
    title: {
      type: String,
      require: true
    },
    category: {
      type: String,
      defualt: ''
    },
    discription: {
      type: String,
      require: true
    }
  },
  computed: {
    getBackgroundImage () {
      return 'url(' + this.src + ')'
    },
    styleObject () {
      return {
        width: this.width + 'px'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import '../assets/css/font-awesome.min.css';

.card {
  width: 250px;
  /* height: 200px; */
  margin: 15px 10px;
  display: flex;
  flex-direction: column;
  color: #000;
  background-color: #fff;
  border-radius: 3px;
  box-shadow: 0 2px 5px 0 rgba(0,0,0,.14), 0 2px 5px 0 rgba(0,0,0,.15);
  transition-duration: .7s;
  transition-property: box-shadow;
  overflow: hidden;
}
@media (max-width: 500px) {
  .card {
    width: 80%!important;
  }
}
.card:hover {
    box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.25), 0 2px 10px 0 rgba(0, 0, 0, 0.26);
}
.card .bg {
    border-top-left-radius: 3px;
    border-top-right-radius: 3px;
    width: 100%;
    height: 140px;
    background-size: cover;
    transition-duration: 0.7s;
    transition-property: opacity;
}
.card .bg:hover {
  opacity: .7;
}

.card .discription {
  font-size: 14px;
  display: flex;
  flex: 1;
  align-items: center;
}
.card .row {
  width: 100%;
  padding: 10px 15px;
}
.discription .column-flex {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
}
.discription .title {
  font-weight: bold;
  font-size: 15px;
  padding-bottom: 5px;
}
.discription .category {
  color: #6f6f6f
}
.discription .more {
  color: #80CBC4;
}
.long-text {
  max-width: 200px;
  overflow: hidden;
  text-overflow:ellipsis;
  white-space: nowrap;
}
.fa.fa-share {
  color: #26A69A;
}
</style>
