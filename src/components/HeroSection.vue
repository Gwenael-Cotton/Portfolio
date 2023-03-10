<template>
  <div class="hero">
    <div class="hero-picture">
      <img id="photo" alt="Mon portrait" src="../assets/photo.jpeg" />
      <div>
        <h1 class="hero-title">Gwenaël Cotton</h1>
        <h2 class="hero-title2">Développeur web</h2>
      </div>
    </div>
    <h1>{{ msg }}</h1>
    <p class="text">
      Je suis développeur web front-end avec 2 ans d'expérience dans le domaine.
      J'ai acquis mes compétences grâce à un apprentissage chez Sfeir Group. Mon
      expertise principale réside dans le développement de React, mais j'ai
      également une expérience de travail avec Terraform, GCP, CI/CD, Docker et
      diverses autres technologies.
      <!-- <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >. -->
    </p>
    <p class="text">
      Je suis fier de pouvoir m'adapter rapidement à n'importe quel projet, de
      ses débuts jusqu'à sa réalisation. Qu'il s'agisse de créer un nouveau site
      Web à partir de zéro ou d'améliorer un site existant, je suis toujours
      prêt à relever un défi.
    </p>
    <p class="text">
      Si vous recherchez une personne qualifiée, compétente et passionnée par
      son travail, ne cherchez pas plus loin. Merci de me considérer pour votre
      prochain projet!
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
  animation: border-top 1s linear forwards;
  animation: border-bottom 1s linear forwards;
  overflow: hidden;
  margin: 0 auto;
}

#photo {
  clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
  width: 300px;
  height: 300px;
  object-fit: cover;
  animation: image 2.5s ease-out forwards;
}

/* Define the animation */
@keyframes border-top {
  from {
    width: 20%;
  }
  to {
    width: 100%;
  }
}

@keyframes border-bottom {
  from {
    width: 20%;
  }
  to {
    width: 100%;
  }
}

@keyframes image {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.hero-title {
  opacity: 0;
  animation: slide-in 0.2s ease-out forwards;
  animation-delay: 0.8s;
  font-size: 36px;
}

.hero-title2 {
  opacity: 0;
  animation: slide-in 0.2s ease-out forwards;
  animation-delay: 1s;
  font-size: 32px;
}

@keyframes slide-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
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
  // animation: 1s back-to-front ease-in;
}

// @keyframes back-to-front {
//   from {
//     opacity: 0;
//     transform: translateZ(-100px);
//   }
//   to {
//     opacity: 1;
//     transform: translatez(0);
//   }
// }

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
