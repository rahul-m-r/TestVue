
<template>

<div>
  <b-navbar type="dark">
    <b-navbar-nav>
        <b-navbar-brand href="#">
        <img src="https://thetunagroup.com/storage/settings/Tuna1559538115.svg" alt="logo">
        </b-navbar-brand>
    </b-navbar-nav>
     <b-navbar-nav class="ml-auto">
        <b-nav-item v-for="item in menu_items" :key="item.id"  :href="item.link"><b>{{item.menuname}}</b></b-nav-item>
     </b-navbar-nav>
  </b-navbar>
</div>
</template>

<script>
import axios from 'axios'

export default {
    data(){
        return {menu_items: [],}
    },
    mounted() {
        axios.get('http://testvue.thetunagroup.com/?api=menus')
        .then(response => {this.menu_items = response.data.menus})
    }
}
</script>

<style scoped>
.navbar {

    /* position: fixed; */
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    padding: 0.5rem 1rem;
    /* z-index: 50;     */
    width: 100%;
}
.navbar-brand img {
    width: 200px;
}
</style>