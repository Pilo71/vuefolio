<template>
    <section>
      
      
        <h1 @click="toggleShowForm" class="name hover">Contact</h1>
        <h2 class="contact1">Remplissez notre formulaire afin d'établir un premier contact !</h2>
        <div v-if="showForm" class="form" id="envoyer">
      <h2 class="color">Formulaire</h2>

      <form id="home" action="">

        <div class="colonnes tipo" v-if="step == 1">
          <label for="first-name">Nom</label>
          <input class="style" type="text" v-model="form.firstName" name="firstName" id="form.firstName" />
        </div>
        <div class="colonnes tipo" v-if="step ==2">
          <label for="last-name">Prénom</label>
          <input class="style" type="text" v-model="form.lastName" name="lastName" id="form.lastName" />
        </div>
        <div class="colonnes tipo" v-if="step == 3">
          <label for="email">Email</label>
          <input class="style" type="email" v-model="form.email" name="email" id="form.email" />
        </div>
        <div class="colonnes tipo" v-if="step == 4">
          <label for="message">Message</label>
          <textarea class="style2" v-model="form.message" name="méssage" id="form.message"></textarea>
        </div>
        <div class="flex">
          <button class="bouton2" @click.prevent="nextStep()" v-if="step < 4">suivant</button>
          <button class="bouton2" @click.prevent="previousStep()" v-if="step > 1">précédent</button>
          <button class="bouton2" @click.prevent="sendData()" v-if="step == 4">envoyer</button>
        </div>
        <span class="space" v-for="form in errors">{{ form }}</span>
      </form>
    </div>
  </section>
</template>
<script>



export default {
  name: "contact",


  data() {
    return {

      
      showForm: false,
      step: 1,
      totalSteps: 4,
      errors: [],
      form: {
        firstName: null,
        lastName: null,
        email: null,
        message: null,
      },
    };
  },

  methods: {

    
    toggleShowForm() {
      this.showForm = !this.showForm;
    },
    nextStep() {
      this.errors = [];
      if (this.step == 1) {
        if (!this.form.firstName) {
          this.errors.push("le nom est requis");
          return false;
        }}
        if(this.step == 2){

        if (!this.form.lastName) {
          this.errors.push("le prénom est requis");
          return false;
        }
      }
      if (this.step == 3) {
        if (!this.form.email) {
          this.errors.push("l'email est requis");
          return false;
        }
      }
      this.step++;
    },
    previousStep() {
      this.step--;
    },
    sendData() {
      this.errors = [];
      if (this.step == 4) {
        if (!this.form.message) {
          this.errors.push("le message est requis");
          return false;
        }

        alert("données envoyées");
      }
    },
  },
};
    </script>