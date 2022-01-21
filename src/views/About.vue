<template>
  <div class="about">
    <HelloAbout msg="Send a ping request to API" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloAbout from "@/components/HelloAbout.vue";

export default {
  name: "About",
  components: {
    HelloAbout,
  },
};
</script>
