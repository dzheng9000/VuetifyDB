<template>
  <div>
    <h3>My Profile</h3>
    <h4>{{ $route.params.id }}</h4>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  mounted() {
    console.log(this.$route.params.id);
  },
  name: "Profile",
  watch: {
    $route(to, from) {
      console.log("to", to);
      console.log("from", from);
    }
  },
  components: {}
};
</script>
