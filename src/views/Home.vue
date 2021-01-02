<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <MyMainComponent />
  </div>
</template>

<script>
// @ is an alias to /src
import MyMainComponent from "@/components/MyMainComponent.vue";

export default {
  name: "Home",
  components: {
    MyMainComponent
  }
};
</script>
