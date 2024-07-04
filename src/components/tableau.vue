 <!-- <template>
  <h1>tableau</h1>
  <div class="tab">
  <table>
    <thead>
        <tr>
            <th>Task</th>
            <th>Status </th>
            <th>comment </th>
            <th>etat</th>
           
        </tr>
    </thead>
    <tbody>
        <tr >
            <td>nom</td>
            <td><input type="checkbox">traité</td>            
            <td><button>supprimer</button><button>modifier</button></td>
            <td><input type="checkbox">confirmé</td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
  </table>
</div>
</template>

<script setup>

</script>



<style scoped>
th,tr,td{
    /* border-collapse: collapse; */
    border: 1px solid black;
    line-height: 100px;
    width: 200px;
}
.tab{
    display: flex;
    align-content: center;

}

</style>




 <template>
    <div>
      <h2>Liste des éléments</h2>
      <table>
        <thead>
          <tr>
            <th>Texte</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(element, index) in elements" :key="index">
            <td>{{ element }}</td>
            <td>
              <button @click="modifier(index)">Modifier</button>
              <button @click="supprimer(index)">Supprimer</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  const props = defineProps({
    elements: {
      type: Array,
      required: true
    }
  });
  
  // Méthode pour modifier un élément
  const modifier = (index) => {
    const nouveauTexte = prompt('Entrez le nouveau texte :', props.elements[index]);
    if (nouveauTexte !== null) {
      emit('modifier', index, nouveauTexte);
    }
  };
  
  // Méthode pour supprimer un élément
  const supprimer = (index) => {
    if (confirm('Êtes-vous sûr de vouloir supprimer cet élément ?')) {
      emit('supprimer', index);
    }
  };
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant */
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  th, td {
    padding: 10px;
    border: 1px solid #ccc;
    text-align: left;
  }
  
  button {
    padding: 5px 10px;
    margin-right: 5px;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
   -->



   <template>
    <div>
      <h2>Liste des tâches</h2>
      <table>
        <thead>
          <tr>
            <th>Tâche</th>
            <th>Modification</th>
            <th>Suppression</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(element, index) in elements" :key="index">
            <td>{{ element.tache }}</td>
            <td>
              <button @click="modifier(index)">Modifier</button>
            </td>
            <td>
              <button @click="supprimer(index)">Supprimer</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script setup>
  import { ref, defineProps, defineEmits } from 'vue';
  
  const props = defineProps({
    elements: {
      type: Array,
      required: true
    }
  });
  
  const emit = defineEmits(['modifier', 'supprimer']);
  
  const modifier = (index) => {
    const nouveauTexte = prompt('Entrez le nouveau texte :', props.elements[index].tache);
    if (nouveauTexte !== null) {
      emit('modifier', index, nouveauTexte);
    }
  };
  
  const supprimer = (index) => {
    if (confirm('Êtes-vous sûr de vouloir supprimer cette tâche ?')) {
      emit('supprimer', index);
    }
  };
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant */
  table {
    width: 100%;
    border-collapse: collapse;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  th, td {
    padding: 10px;
    border: 1px solid #ccc;
    text-align: left;
  }
  
  button {
    padding: 5px 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  
