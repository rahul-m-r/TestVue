<template>
<div class="search-bar" v-if="showSearch">
  <h1 class="h-1" style="text-align: left"><b>BOOK GREAT FILMS AND EVENTS</b></h1>
  <b-button-toolbar aria-label="Toolbar with button groups and dropdown menu">
    <b-button-group size="lg" class="mx-1">

        <b-dropdown variant="light" text="CINEMAS">
            <b-dropdown-item></b-dropdown-item>
        </b-dropdown>

        <b-dropdown variant="light" text="FILMS">
            <b-dropdown-item></b-dropdown-item>
        </b-dropdown>

        <b-dropdown variant="light" text="DATES">
            <b-dropdown-item></b-dropdown-item>
        </b-dropdown>


        <b-dropdown variant="light" text="TIMES">
            <b-dropdown-item></b-dropdown-item>
        </b-dropdown>

    </b-button-group>
    <b-button-group class="mx-1">
      <b-button variant="light"><b-icon icon="search"></b-icon></b-button>
    </b-button-group>
  </b-button-toolbar>
</div>
</template>

<script>
export default {
    data() {
      return {
        showSearch: true
      }
    },
    created() {
      window.addEventListener("resize", this.vpEventHandler);
    },
    destroyed() {
      window.removeEventListener("resize", this.vpEventHandler);
    },
    methods: {
      vpEventHandler() {
        if (window.innerWidth < 866) {
          this.showSearch = false
        } else {
          this.showSearch = true;
        }
      }
    }

}
</script>

<style scoped>
.h-1 {
  font-family: 'Ramabhadra', sans-serif;
}
.search-bar {
    position: absolute;
    top: 50%;
    left: 20%;
    z-index: 20;
    color: white;
}
.dropdown.b-dropdown.btn-group{
  width: 13vw;
}
</style>