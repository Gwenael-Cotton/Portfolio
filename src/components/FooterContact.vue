<template>
  <footer>
    <span class="copyright"> © Cotton Gwenaël 2023 - Tous droits réservés</span>
    <ul class="contact-list">
      <li v-for="(icon, index) in icons" class="contact-list-item" :key="index">
        <a :href="icon.url" target="_blank">
          <img :src="icon.path" :alt="icon.alt" class="icon" />
        </a>
      </li>
    </ul>
  </footer>
</template>

<script lang="ts">
export default {
  data() {
    return {
      icons: [
        {
          path: "001-instagram.png",
          alt: "icon instagram",
          url: "#",
        },
        {
          path: "002-linkedin.png",
          alt: "icon linkedin",
          url: "https://www.linkedin.com/in/gwenaelcotton",
        },
        {
          path: "003-github.png",
          alt: "icon github",
          url: "https://github.com/Gwenael-Cotton",
        },
        {
          path: "004-email.png",
          alt: "icon email",
          url: "mailto:gwenael.cotton@gmail.com",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
footer {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 20vh;
  background-color: #34435e;
  color: #fff;
}
.contact-list {
  width: 300px;
  display: flex;
  list-style-type: none;
}

.contact-list-item {
  margin: 0 auto;
}

.icon {
  filter: invert(100%) brightness(100%) contrast(100%);
  opacity: 0.75;
  transition: all 0.4s;
  &:hover {
    opacity: 1;
    cursor: pointer;
    transition: all 0.4s;
  }
}

@media (max-width: 768px) {
  footer {
    flex-direction: column-reverse;
    justify-content: space-around;
  }
  .contact-list {
    padding: 0;
  }
  .copyright {
    font-size: 0.8rem;
  }
}
</style>
