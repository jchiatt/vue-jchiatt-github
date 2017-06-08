<template>
  <div id="app">
    <profile v-bind:profileData="profileData" v-bind:isHireable="isHireable"></profile>
  </div>
</template>

<script>
import axios from 'axios';
import Profile from './components/Profile';

export default {
  name: 'app',
  components: {
    Profile,
  },

  data() {
    return {
      profileData: [],
      errors: [],
      isHireable: false,
    };
  },

  created() {
    axios.get('https://api.github.com/users/jchiatt')
      .then((response) => {
        this.profileData = response.data;
        if (response.data.hireable === true) {
          this.isHireable = true;
          console.log(this.isHireable);
        }
      })
      .catch((e) => {
        this.errors.push(e);
      });
  },
};
</script>

<style>

</style>
