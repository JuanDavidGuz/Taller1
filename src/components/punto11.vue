<template>
    <h1>Punto 11:</h1>
    <div>
            <h2 v-if="info.length == 0">Nombre estudiante:</h2><input type="text" v-model="nombre" placeholder="su nombre" v-if="info.length == 0"/>
            <h2>Nombre materia:</h2><input type="text" v-model="Materia"/>
            <h2>Nota materia:</h2><input id="nota" type="number" min="0" max="5" v-model="nota"/>
            <br>
            <button class="button" @click="Listado">Añadir</button>
            <button class="button" @click="Borrar">Borrar</button>
    </div>
    <div>
        <h2 class="alerta" v-if="(nombre != null || Materia != null || nota != null) && (info.length<3)">LLene todos los campos</h2>
        <h2 class="alerta" v-if="nota != null && (nota < 1 || nota > 5)">Ingrese una nota entre 1 y 5</h2>
    </div>
    <div>
        <ul v-if="info.length == 3">
            <h2>{{nombre}}</h2>
            <li  v-for="(m) in info">
                <h2>{{m}}</h2>

            </li>
        </ul>
    </div>
    </template>
    <script>

    export default {
        data(){
            return{
                nombre: null,
                nota: null,
                info: [],
              
            }
        },
        methods:{
            Listado(){
                if(this.nombre != null || this.Materia != null || this.nota != null){
                    if(this.info.length<3 && this.nota>0 && this.nota<=5){
                        if(this.nota>=3){
                            let cont = this.Materia + ': ' + this.nota.toFixed(1) + 'APROBASTE'
                            this.info.push(cont);
                        }
                        else{
                            let cont = this.Materia + ': ' + this.nota.toFixed(1) + 'REPROBASTE'
                            this.info.push(cont);
                        }
                        this.Materia = null;
                        this.nota = null;
                    }

                }
            
                    },
                    Borrar(){
                    this.info = []
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