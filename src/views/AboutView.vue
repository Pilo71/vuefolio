<template>
  <section>
    <!--section visible au click-->
    <h1 @click="toggleShowProjets" class="name hover">Projets</h1>
    <h2 class="contact1">Explorez quelques exemples ! </h2>
    <div v-if="showProjets">
      <ul>

        <li v-for="projet in projets">

          <p class="name position2">{{ projet.title }}</p>
          <router-link to="/galerie">
            <img class="projets" :src="projet.img" alt="images projets">
          </router-link>
        </li>
      </ul>
    </div>
  </section>
  <router-view></router-view>
</template>
<script>



export default {
  name: "about",


  data() {
    return {

      showProjets: false,
      projets: [
        { title: "Réaliser votre Cv en ligne", img: "/src/images/cv.png" },

        { title: "Réaliser votre Cahier des charges en ligne", img: "/src/images/001C.Charges.png" },
        { title: "Réaliser votre site web", img: "/src/images/mon village png 1.png" },
      ],

    };
  },

  methods: {

    toggleShowProjets() {
      this.showProjets = !this.showProjets;
    },

  },
};

</script>


