<template>
    <h1>Punto 7:</h1>
        <div class="indecision-container">
          <h2>Ingrese los salarios:  </h2>
          <label>Salario: </label><input type="number" v-model="salario" placeholder="Agregar Salario"  min="0"/>
          <br>
                <button class="button" @click="IngresarSal">INGRESAR</button>
                <button class="button" @click="MostrarSal">MOSTRAR TODOS LOS SALARIOS</button>
                <button class="button" @click="Borrar">LIMPIAR</button>
        </div>
    <div>
       <textarea readonly id="area" cols="30" rows="18">{{respuesta}}</textarea>
    </div>
    </template>
    <script>


    export default {
        nombre: 'salarios',
        data(){
            return{
                salario: null,
                salarios:[],
                respuesta: ''

    
            }
        },
        methods:{
            IngresarSal(){
                if(this.salarios.length < 10){
                    if(this.salario>0){
                        this.salarios.push(this.salario)
                        this.respuesta = '';
                    }
                    else{
                    this.respuesta = 'Ingresar un numero mayor a 0';
                    }
                }
                    else{
                        this.respuesta = 'No se puden añadir mas salarios :(  (max 10)'
                    }
                    this.salario = null;

                    },

                    MostrarSal(){
                        if(this.salarios.length ==10){
                            this.respuesta = '';

                            for(let i=0; i<this.salarios.length; i++){
                                this.respuesta += '$' + this.salarios[i]+' anumneto 8% es: $' + (this.salarios[i]*1.08).toFixed(2) + '\n';

                            }
                        }
                        else{
                            this.respuesta = '¡Error! Ingrese al menos 10 salsarios'
                        }
                    },

                    Borrar(){
                    this.respuesta ='';
                    this.salarios = []
                        

                    },
                   
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