<template>
  <ul>
    <!-- dynamically loop over and create new li for each friend
    uses key, just like react -->
    <li v-for="friend in friends" :key="friend.name">{{friend.name}} - {{friend.age}}</li>
  </ul>
</template>

<script>
// describe our props
export default {
  props: {
    friends: Array
  }
};
</script>
<style scoped>
/* styles that are specific to this component using scoped */
ul {
  list-style-type: none;
  padding: 0;
}
</style>
