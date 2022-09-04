<template>
    <div class="bg-dark"></div>
    <h1>Punto 6:</h1>
        <div class="indecision-container">
          <h2>Ingrese el numero:  </h2>
                <input type="number" v-model="n" placeholder="Ingresa el numero" @keypress.enter="Listado()"/>
                <br>
                <button class="button" @click="Listado">INGRESAR</button>
                <button class="button" @click="Borrar">Limpiar</button>
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
            respueta: '',
            n: null
    
            }
        },
        methods:{
            Listado(){
                if(this.n == null){
                    this.respueta = "Por favor ingrese un dato:"
                }
                else{
                    console.log(this.AregM)    
                    this.AregM.push(this.n);
                        if(this.n % 2 == 0){
                            let c = this.n-1
                            this.AregM.push(c)
                            while(c >= 2){
                            c = c-2
                            this.AregM.push(c)

                            }

                        }
                        else{
                            while(this.n >= 2){
                            this.n = this.n-2
                            this.AregM.push(this.n)
                        }
                        this.n = null

                    }

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