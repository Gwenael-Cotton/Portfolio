<template>
  <HelloWorld msg="Welcome to my portfolio" />
  <ProjectList :projects="projects" />
  <FooterContact />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import ProjectList from "./components/ProjectList.vue";
import FooterContact from "./components/FooterContact.vue";

export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
    ProjectList,
    FooterContact,
  },
  data() {
    return {
      projects: [],
    };
  },
});
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  overflow: hidden;
  width: 100%;
  box-sizing: border-box;
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 16px;
}
</style>
