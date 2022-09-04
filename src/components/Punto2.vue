<template>
    <div>
        <h1>Punto 2:</h1>
        <h2>Para calcular lo que tiene que pagar ingrese los minutos: </h2>
        <input type="number" v-model="tiempo" placeholder="Ingresa el tiempo en minutos" @keypress.enter="Calcular()"/>
    </div>
    <div>
        <h2>{{tiempo}}</h2>
        <br>
        <label>Su costo fue:  {{costo}}</label>
        <br>
    </div>
    </template>
    <script>
    export default {
        data(){
            return{
                costo: '',
    
            }
        },
        methods:{
            Calcular(){
                 if (this.tiempo > 0) {
                    if(this.tiempo < 3){
                        this.costo =  100
                        
                    }
                    else{
                        this.adicional = (this.tiempo - 3)
                        this.costo = 100 + (this.adicional * 50)
                    }

                }
                else{

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

    </style>    