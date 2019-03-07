<template>
<!-- template element is where our HTML will go. Can use any valid HTML and CSS -->
  <div id="app">
    <!-- bind data to specific componnt. Similar to props -->
    <Friend v-bind:friends="friends"/>
    <FriendForm v-bind:friendInfo="friendInfo" @addFriend="addFriend"/>
  </div>
</template>

<script>
import Friend from "./components/Friend.vue";
import FriendForm from "./components/FriendForm.vue";

// exporting our app and giving it a name. We do thi so we can use it main.js
export default {
  name: "app",
  components: {
    Friend,
    FriendForm
  },
  // data we want to pass down to our components
  data: function() {
    return {
      friends: [
        { name: "Landy", age: 27 },
        { name: "Lindsey", age: 24 },
        { name: "Taz", age: 28 },
        { name: "Corey", age: 28 }
      ],
      friendInfo: {
        friendName: "",
        friendAge: ""
      }
    };
  },
  //custom method we will pass down to a component
  methods: {
    // addFriend looking for an object param
    addFriend(obj) {
      if (obj.name && obj.age) {
        this.friends.push(obj);
      } else {
        alert("Please add name and age");
      }
    }
  }
};
</script>

<style>
/* style not scoped */
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
