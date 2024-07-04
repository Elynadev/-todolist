<template>
  <div id="app">
    <Formulaire @ajouter="ajouterElement" />
    <Tableau
      :elements="elements"
      @modifier="modifierElement"
      @supprimer="supprimerElement"
    />
  </div>
</template>
    
    <script setup>
import { ref } from "vue";
import Tableau from "./components/Tableau.vue";
import Formulaire from "./components/Formulaire.vue";

const elements = ref([]);

const ajouterElement = (nouvelleTache) => {
  elements.value.push({ tache: nouvelleTache });
};

const modifierElement = (index, nouveauTexte) => {
  elements.value[index].tache = nouveauTexte;
};

const supprimerElement = (index) => {
  elements.value.splice(index, 1);
};
</script>
    
    <style>
/* Styles globaux */
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  padding: 20px;
}

#app {
  max-width: 800px;
  margin: 0 auto;
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
}
</style>
    
