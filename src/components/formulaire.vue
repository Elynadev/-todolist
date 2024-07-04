   <template>
    <div>
      <h2>Ajouter une tâche</h2>
      <form @submit.prevent="ajouter">
        <input type="text" v-model="nouvelleTache" placeholder="Entrez votre tâche...">
        <button type="submit">Ajouter</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref, defineEmits } from 'vue';
  
  const emit = defineEmits(['ajouter']);
  
  const nouvelleTache = ref('');
  
  const ajouter = () => {
    if (nouvelleTache.value.trim() !== '') {
      emit('ajouter', nouvelleTache.value.trim());
      nouvelleTache.value = '';
    }
  };
  </script>
  
  <style scoped>
  /* Styles spécifiques au composant */
  form {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  
  input {
    flex: 1;
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
  }
  
  button {
    padding: 10px 20px;
    margin-left: 10px;
    background-color: #28a745;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #218838;
  }
  </style>
  

   