<template>
  <div class="hero">
    <div class="hero-picture">
      <img id="photo" alt="Mon portrait" src="../assets/photo.jpeg" />
      <h1>Hi, my name is Mouth ... Cotton Mouth</h1>
    </div>
    <h1>{{ msg }}</h1>
    <p class="text">
      Hi, My name is Gwen and I am a front-end web developer with 2 years of
      experience in the field. I have acquired my skills through an
      apprenticeship at Sfeir Group. My main expertise lies in React
      development, but I also have experience working with Terraform, GCP,
      CI/CD, Docker and various other technologies.
      <!-- <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >. -->
    </p>
    <p class="text">
      I pride myself on being able to adapt quickly to any project, from its
      beginning stages all the way through to its completion. Whether it's
      building a new website from scratch or improving an existing one, I am
      always ready for a challenge.
    </p>
    <p class="text">
      If you're looking for someone who is skilled, knowledgeable, and
      passionate about their work, then look no further. Thank you for
      considering me for your next project!
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$black: #34435e;
$white: #ffffff;
.hero {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0 2rem;
}
.hero-picture {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 300px;
  border-top: 1px solid $black;
  border-bottom: 1px solid $black;
  overflow: hidden;
  margin: 0 auto;
}
#photo {
  clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
  // border-radius: 50%;
  width: 300px;
  height: 300px;
  object-fit: cover;
}
h1 {
  margin: 40px 0 0;
  animation: 0.4s left-to-right forwards;
}

@keyframes left-to-right {
  from {
    opacity: 0;
    transform: translateX(-100px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.text {
  font-size: 1.2rem;
  animation: 1s back-to-front ease-in;
}

@keyframes back-to-front {
  from {
    opacity: 0;
    transform: translateZ(-100px);
  }
  to {
    opacity: 1;
    transform: translatez(0);
  }
}

@media (max-width: 768px) {
  .text {
    font-size: 1rem !important;
  }
}
@media (max-width: 1000px) {
  #photo {
    width: 200px !important;
    height: 200px !important;
  }
  // .hero-picture {
  //   width: 200px !important;
  //   height: 200px !important;
  // }
}
</style>
