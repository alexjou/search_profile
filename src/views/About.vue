<template>
  <div class="about">
    <Navbar/>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "../components/Navbar.vue";
export default {
  name: 'About',
  components: {
    Navbar
  },
  props: {
    msg: String
  },
  created() {
    console.log(this.msg);
  },
}
</script>