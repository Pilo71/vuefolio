<template>
    <h1> CV en ligne</h1>
    <a href="#" target="_blank"><img class="galerie2" src="../images/cv.png" alt=""></a>
    <h1> Cahier des charges</h1>


    <img @click="toggleShowGalerie" v-if="step == 1" class="galerie2 cursor" src="/src/images/001C.Charges.png"
        alt="presentation cahier des charges">


    <div v-if="showGalerie">
        <div v-if="step == 2">
            <img class="galerie" src="/src/images/002C.Charges 2.jpg" alt=" sommair cahier des charges">
        </div>
        <div v-if="step == 3"><img class="galerie" src="/src/images/003cahier des charges3 p2-combiné-2jpg.jpg"
                alt="objectif et cible cahier des charges">
        </div>
        <div v-if="step == 4"><img class="galerie" src="/src/images/04 cahier des charges graphisme p4.jpg"
                alt="charge graphique">
        </div>
        <div v-if="step == 5"><img class="galerie" src="/src/images/005cahier des charges 5 p2-combiné-4jpg.jpg"
                alt="maquette">
        </div>
        <div v-if="step == 6"><img class="galerie" src="/src/images/007.jpg" alt="déroulement du projet">


            <div>
                <img class="galerie" src="/src/images/cahier des charges p2-combiné-7jpg.jpg" alt="devis">
            </div>
        </div>
        <div> <button class="bouton3" @click.prevent="nextStep()" v-if="step < 6">suivant</button>
            <button class="bouton3" @click.prevent="previousStep()" v-if="step > 1">précédent</button>
        </div>
    </div>
    <section>
        <h1> Site web</h1>
        <a href="https://www.monvillage85.com/" target="_blank"><img class="galerie" src="/src/images/mon village png.png"
                alt=""></a>
    </section>
</template>
<script>
export default {
    name: "galerie",
    data() {
        return {
            showGalerie: false,
            step: 1,
            totalSteps: 6,
        };
    },
    methods: {
        toggleShowGalerie() {
            this.showGalerie = !this.showGalerie;
        },
        nextStep() {
            this.step++;
        },
        previousStep() {
            this.step--;
        },
    },

}
</script>