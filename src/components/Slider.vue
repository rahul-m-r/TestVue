<template>

<div>
  <b-carousel
    id="carousel-fade"
    style="text-shadow: 0px 0px 2px #000"
    fade
    indicators
    img-width="1024"
    img-height="480"
  >
    <b-carousel-slide
      caption-html=""
      :img-src="item.image"
      v-for="item in items" :key="item.id"
    >
    <div>
        <h1>{{item.title}}</h1>
        <p>{{item.sub_title}}</p>
        <p>{{item.text}}</p>
        <b-button variant="light" class="slide-btn">{{item.button_name}}</b-button>
    </div>

    </b-carousel-slide>
  </b-carousel>
</div>
</template>

<script>
  import axios from 'axios'

  export default {
    data() {
      return {
        items: [],
      }
    },
    methods: {
    },
    mounted(){
      axios.get('http://testvue.thetunagroup.com/?api=sliders')
      .then(response => (this.items=response.data.sliders))
    }
  }
</script>

<style scoped>
.slide-btn {
  color: red;
}
.carousel-caption div {
  text-align: left;
}
</style>