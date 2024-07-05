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
  
