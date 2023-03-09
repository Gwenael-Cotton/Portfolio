<template>
  <footer>
    <span class="copyright"> © Cotton Gwenaël 2023 - Tous droits réservés</span>
    <ul class="contact-list">
      <li v-for="(icon, index) in icons" class="contact-list-item" :key="index">
        <img :src="icon.url" :alt="icon.alt" class="icon" />
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
          url: "001-instagram.png",
          alt: "icon instagram",
        },
        {
          url: "002-linkedin.png",
          alt: "icon linkedin",
        },
        {
          url: "003-github.png",
          alt: "icon github",
        },
        {
          url: "004-email.png",
          alt: "icon email",
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
</style>
