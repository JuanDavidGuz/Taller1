<template>

    <h1>Punto 9:</h1>
    <h1> Crear Tabla:</h1>
    <h2>Ingrese el numero de Filas y columnas:</h2>
    <span>Filas: </span><input class="tab" type="number" v-model="nf"/>
    <span>Columnas: </span><input class="tab" type="number" v-model="nc"/>
    <table v-if="nf > 0 && nc/0">
        <tr v-for="(idi) in nf">
            <td width="50" v-for="(l) in nc">{{idi}},{{l}}</td>
        </tr>
    </table>
    <p v-else>Ingrese un valor valido</p>

</template>

<script>
export default {
    name: 'Tabla',
    data(){
        return{
            nf: null,
            nc: null
        }
    }
}
</script>

<style>
h1{
      font-family: 'Courier New', Courier, fantasy;
      color: rgb(255, 0, 0);
    }
    h2{
      font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    }
    label{
      font-family: 'Times New Roman', Times, serif;
    }
    .button{
        color: aliceblue;
        background-color: black;
        border-radius: 50px;
        border: 2px solid #ea0e0e;
        transition-duration: 0.4s;
        cursor: pointer;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        
     }
     .button:hover {
        color: black;
        background-color: aliceblue;
     }
     p{
        font-family: 'Times New Roman', Times, serif;
     }
     table,th,td{
        color: rgb(237, 237, 237);
        border: 2px solid #ea0e0e;
     }
</style>