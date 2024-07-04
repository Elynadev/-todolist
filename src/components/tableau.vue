<template>
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
        <tr>
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

