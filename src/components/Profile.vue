<template>
  <div class="profile">
    <h1 v-if="profileData">{{profileData.name}}'s GitHub Stats</h1>
    <!--<img :src="profileData.avatar_url">-->
    <p>{{profileData.name}} is from {{profileData.location}}. Their username is {{profileData.login}} and they are currently {{isHireable ? '' : 'not'}} hireable.</p>

    <p><a :href="profileData.html_url">View this profile on GitHub.com.</a></p>
  </div>
</template>

<script>
export default {
  name: 'profile',
  props: ['profileData', 'isHireable'],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
