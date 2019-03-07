<template>
  <form @submit="add">
    <!-- v-model tells the elment what data it should model itself after -->
    <input type="text" placeholder="name" v-model="friendInfo.friendName">
    <input type="text" placeholder="age" v-model="friendInfo.friendAge">
    <button>Add Friend</button>
  </form>
</template>

<script>
// describing what shape the props we will receive should be
export default {
  props: {
    friendInfo: Object
  },
  methods: {
    add(e) {
      e.preventDefault();
      // $emit takes in the function we want to run and the argument needed
      this.$emit('addFriend', {name: this.friendInfo.friendName, age: this.friendInfo.friendAge})
      this.friendInfo.friendName = ""
      this.friendInfo.friendAge = ""
    }
  }
};
</script>

