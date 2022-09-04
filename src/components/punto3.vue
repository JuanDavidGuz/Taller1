<template>
        <div>
        <h1>Punto 3:</h1>
        <h2>Ingrese su Nombre por favor:  </h2>
        <input type="text" v-model="Nombre" placeholder="Ingresa el tiempo en minutos" />
        </div>
        <div>
            <h2>Ingresa la Hora en formato: </h2>
            <input type="time" v-model="Hora" placeholder="HH/MM/SS" />
            <br>
            <button class="button" v-on:click="Calcular()">INGRESAR</button>
        </div>
    <div>
        <h2>{{tiempo}}  {{Nombre}}</h2>
    </div>
    </template>
    <script>

    export default {
        data(){
            return{
                tiempo: '',
    
            }
        },
        methods:{
            Calcular(){

                if( this.Hora >= '0:00' && this.Hora <='11:59'){
                    this.tiempo = "Buenos dias"
                }
                else{
                if ( this.Hora >= '12:00' && this.Hora <='18:00') {
                    this.tiempo = "Buenas Tardes"
                } else {
                    this.tiempo = "Buenas Noches"
                }
            }
        }
    
        },
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