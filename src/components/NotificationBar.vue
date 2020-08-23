<template>
  <div>

    <b-alert
      :show="showNotification"
      dismissible
      variant="danger"
    >
      <b>{{notifications}}</b>
    </b-alert>

  </div>
</template>

<script>
import axios from 'axios';

  export default {
    data() {
      return {
        showNotification: false,
        notifications: '',
      }
    },
    methods: {
      showAlert() {
        this.showNotification = true;
      }
    },
    mounted () {
      axios.get('http://testvue.thetunagroup.com?api=notifications')
      .then(response => {
        this.notifications = response.data.notifications;
        this.showAlert();
        })
      .catch(error => (console.log(error)));
    }
  }
</script>

<style scoped>
.alert {
  background: #e03d3d;
  color: white;
  text-align: left;
  padding-left: 100px;
  border-radius: 0;
  font-size: 16px;
  font-family: 'Ramabhadra', sans-serif;
  /* position: fixed;
  z-index: 100; */
  width: 100%;
  border: 0;  
}

</style>