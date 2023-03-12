<template>
  <div>
    <div class="project-list">
      <div
        class="projectItem"
        v-for="(project, index) in projects"
        :key="index"
      >
        <h4 class="title">{{ project.title }}</h4>
        <p class="date">{{ project.date }}</p>
        <p class="description">{{ project.description }}</p>
        <img
          v-show="project.images"
          v-for="(image, i) in project.images"
          :src="image.url"
          :alt="image.alt"
          :key="i"
          class="project-picture"
        />
        <div class="stacks">
          <div
            class="stackItem"
            v-for="(item, index) in project.stack"
            :key="index"
          >
            {{ item }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      projects: [
        {
          title: "Erwan web site",
          date: "En cours",
          description:
            "Projet simple d'une application portfolio pour un client 'Monteur video YouTube'",
          stack: ["Next.js", "Vercel"],
          images: [
            {
              url: "erwancotton.png",
              alt: "capture d'écran du site d'erwan cotton",
            },
          ],
        },
        {
          title: "Mon portfolio",
          date: "2023",
          description:
            "Fin de mes études, je realise mon portfolio avec pour objectif de commencer à me former sur un 2ème framework front. L'objectif étant de ne pas rester cloisoné avec React et de passer au dela d'une veille technologique en pratiquant",
          stack: ["Vue.js", "TypeScript", "Sass"],
        },
        {
          title: "The Eye",
          date: "2022 - 2023",
          description:
            "Dans le cadre d'un projet, j'ai travaillé sur le développement d'une application qui fournit aux clients une visibilité sur la progression de leurs projets à travers des indicateurs de suivi tels que la consommation budgétaire. Mon rôle a été de concevoir et développer l'interface front-end, en collaboration étroite avec les managers de projets pour m'assurer que toutes les données pertinentes soient affichées de manière claire et concise. Au-delà de la conception et du développement de l'interface utilisateur, j'ai également travaillé en étroite collaboration avec les autres membres de l'équipe. Mon engagement envers l'excellence et mon attention aux détails ont été des atouts précieux pour ce projet, qui a été un succès.",
          stack: ["Next.js", "Strapi", "GCP", "Terraform"],
          images: [
            {
              url: "theeye.png",
              alt: "capture page detail d'un projet The eye",
            },
            {
              url: "theeyes2.png",
              alt: "capture page detail d'un projet The eye",
            },
          ],
        },
        {
          title: "Delfingen",
          date: "2021",
          description:
            "Au sein de mon parcours en alternance chez Sfeir, j'ai travaillé sur un projet de refonte d'un service de facturation déjà existant. Mon rôle était de prendre en charge la gestion des tickets bugs ainsi que la création des composants React respectant les maquettes, et effectuer des tests de charges pour garantir le bon fonctionnement du service.",
          stack: [
            "Next.js",
            "Fastify",
            "Prisma",
            "GCP",
            "CircleCI",
            "Docker",
            "Lerna",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
//Colors
$black: #34435e;
$white: #ffffff;

.project-list {
  max-width: 800px;
  margin: auto;
}

.projectItem {
  line-height: 2rem;
  border-top: 3px solid;
  border-image: linear-gradient(to right, $white -50%, $black 100%);
  border-image-slice: 1;
  border-width: 3px;
  margin: 0;
  padding: 40px;
  counter-increment: section;
  position: relative;
  color: $black;
  font-size: 16px;

  .title {
    font-size: 2rem;
  }

  .description {
    font-size: 1.2rem;
  }

  .project-picture {
    max-width: 100%;
    margin: 1rem 0 1rem 0;
    border-radius: 5px;
    box-shadow: rgb(0 0 0 / 100%) 0px 5px 15px 0px;
  }

  .stacks {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  }

  .stackItem {
    font-size: 1.2rem;
    border: 1px solid $black;
    padding: 0.5rem;
    margin: 0.5rem;
    border-radius: 5px;
  }

  //numbers
  &:before {
    content: counter(section);
    position: absolute;
    border-radius: 50%;
    padding: 10px;
    height: 1.25em;
    width: 1.25em;
    background-color: $black;
    text-align: center;
    line-height: 1.25em;
    color: $white;
    font-size: 1em;
  }
}
//odd number borders
.projectItem:nth-child(odd) {
  border-right: 3px solid;
  padding-left: 0;
  display: flex;
  flex-direction: column;
  align-items: end;
  text-align: end;
  &:before {
    left: 100%;
    margin-left: -20px;
  }
}
//even number borders
.projectItem:nth-child(even) {
  border-left: 3px solid;
  padding-right: 0;
  display: flex;
  flex-direction: column;
  align-items: start;
  text-align: start;
  &:before {
    right: 100%;
    margin-right: -20px;
  }
}
//handle first and last
.projectItem:first-child {
  border-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.projectItem:last-child {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

@media (max-width: 768px) {
  .projectItem {
    line-height: 1.5rem;
  }
  .title {
    font-size: 1rem !important;
  }

  .description {
    font-size: 0.8rem !important;
  }
  .stackItem {
    font-size: 0.8rem !important;
    padding: 0.3rem !important;
    margin: 0.3rem !important;
  }
  .date {
    font-size: 0.8rem;
  }
}

@media (max-width: 900px) {
  .project-list {
    max-width: 500px;
  }
}

@media (max-width: 600px) {
  .project-list {
    max-width: 300px;
  }
}
</style>
