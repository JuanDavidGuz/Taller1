<template>

        <h1>Punto 8:</h1>
        <h2>Dividir por el número en la posición indicado:</h2>
        <input type="number" v-model="indice" min="0"/>
        <label v-if="indice<=0">  Ingrese un número mayor a 0</label> 
        <br>
        <button class="button" @click="dividir">Calcular</button>
        <button class="button" id="bGenerar" @click="nuevaLista">Generar nuevos numeros</button>
  
        <table id="tabla">
            <tr width="150">
                <th v-if="lista.length>0">Lista actual:</th>
                <td v-for="(n,i) in lista">
                    <span>{{i+1}}. {{n}}</span>
                </td>
            </tr>
            <tr>
                <th v-if="lista2.length>0">Lista dividida por: {{lista[indice-1]}}</th>
                <td v-for="(n) in lista2">
                    <span>{{n}}</span>
                </td>
            </tr>
        </table>
    


</template>
<script>
    export default {
    name: 'Indice',
    data(){
        return {
            indice: null,
            lista: [],
            lista2: []
        }
    },
    methods:{
        nuevaLista(){
            this.lista = [];
            this.lista2 = [];

            for(let i=0; i<10; i++){
                this.lista.push((Math.random()*10).toFixed(2));
            }
        },
        dividir(){
            
            this.lista2 = [];

            if(this.indice>0 && this.lista.length>0){
                

                for(let i=0; i<10; i++){
                    this.lista2.push((this.lista[i]/this.lista[this.indice-1]).toFixed(2));
                }
            }
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