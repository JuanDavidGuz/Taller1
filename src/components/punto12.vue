<template>
        <h1>Punto 12</h1>
        <p>Nombre Estudiante: </p><input type="text" v-model="name" />
        <button class="button" @click="addCourse">Añadir</button>
        <button class="button" @click="generarReporte">Reporte</button>

        <div>
            
            <div class="cuadro">
                <span>Nota1: </span><input id="nota" type="number" min="0" max="5" v-model="nota1" />
            </div>
    
            <div class="cuadro">
                <span>Nota2: </span><input id="nota" type="number" min="0" max="5" v-model="nota2" />
            </div>

            <div class="cuadro">
                <span>Nota3: </span><input id="nota" type="number" min="0" max="5" v-model="nota3" />
            </div>

        </div>

        
        <div>
            <textarea readonly id="area" v-if="reporte" cols="30" rows="18" >{{reporte}}</textarea>
        </div>

  
</template>

<script>
export default {
   name: 'Alumno',
   data(){
    return{
        name:null,
        nota1: null,
        nota2: null,
        nota3: null,
        todos: [],
        reporte: ''
    }
   },
    methods:{
        addCourse(){
            if(this.name != null || this.nota1 != null || this.nota2 != null || this.nota3 != null){
                if(this.todos.length<3 && this.nota1>0 && this.nota1<=5 && this.nota2>0 && this.nota2<=5 && this.nota3>0 && this.nota3<=5){

                    let alumno = {nombre: this.name, 
                                n1: this.nota1,
                                n2: this.nota2,
                                n3: this.nota3,
                                definitiva: (this.nota1 + this.nota2 + this.nota3)/3,
                                res: ''
                                };
                                

                    if(alumno.definitiva>=3){
                        alumno.res = 'APROBADO';
                    }
                    else{
                        alumno.res = 'REPROBADO';
                    }
                    this.todos.push(alumno)

                    this.name = null;
                    this.nota1 = null;
                    this.nota2 = null;
                    this.nota3 = null;

                    console.log(this.todos)
                    }
                }
        },
        generarReporte(){
            this.reporte = '';
            for(let i = 0; i < this.todos.length; i++){
                this.reporte += 'Alumno: ' + this.todos[i].nombre + 
                '\n\nNotas:\n' + 
                'Nota 1: ' + this.todos[i].n1.toFixed(1) + '\n' +
                'Nota 2: ' + this.todos[i].n2.toFixed(1) + '\n' +
                'Nota 3: ' + this.todos[i].n3.toFixed(1) + '\n' +
                'Definitiva: ' + this.todos[i].definitiva.toFixed(1) + '\n' +
                this.todos[i].res + '\n\n';

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