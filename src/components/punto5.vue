<template>
    <div class="bg-dark"></div>
        <div class="indecision-container">
        <h1>Punto 5:</h1>
          <h2>Ingrese el numero que va a añadir:</h2>
                <input  type="number" v-model="DatoN" placeholder="Ingresa el numero" @keypress.enter="Listado()"/>
                <br>
                <button class="button" @click="Listado">INGRESAR</button>
                <button class="button" @click="Listado">INGRESAR</button>

                
        </div>
    <div>
        <ul>
            <li  v-for="(m) in AregM">
                <h2>{{m}}</h2>

            </li>
        </ul>
    </div>
    </template>
    <script>

    export default {
        data(){
            return{

            AregM: [],
            DatoN: null
            ,
            respueta: ''
    
            }
        },
        methods:{
            Listado(){
                if(this.DatoN == null){
                    this.respueta = "Por favor ingrese un dato:"

                }
                else{
                    this.AregM.push(this.DatoN);

                    this.AregM.sort((da1,da2)=>{return da1 - da2});

                    this.DatoN = null

                    }

                        

                    },
                    Borrar(){
                    this.AregM = []

                }
                }


        }
    
        
    
    
    </script>
    <style scoped>
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
        
    </style>