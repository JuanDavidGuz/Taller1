  <template>
    <div class="bg-dark"></div>
    <h1>Punto 4:</h1>
        <div class="indecision-container">
              <h2>Ingrese el primer numero: </h2>
              <input type="number" v-model="n1" placeholder="Primer numero" />
              <h2>Ingresa el segundo numero: </h2>
              <input type="number" v-model="n2" placeholder="Segundo numero" />
              <h2>Ingresa el terver numero: </h2>
              <input type="number" v-model="n3" placeholder="Tercer numero" />
              <br>
                <button class="button" v-on:click="Calcular()">Comparar</button>
        </div>
    <div>
        <h2>{{Pregunta}}</h2>
    </div>
  </template>

    <script>
    export default {
        data(){
            return{
                n1: null,
                n2: null,
                n3: null,
                Pregunta: '',
    
            }
        },
        methods:{
            Calcular(){
                if (this.n1 == null || this.n2 == null || this.n3 == null ) {
                    this.Pregunta = "Ingrese  los 3 numeros porfis :D"
                } else {
                    let contador = 1;

                    if (this.n1 == this.n2 ) {
                        contador  ++;
                    } 
                    if(this.n1 == this.n3){
                        contador  ++;
                    }
                    if(contador == 1){
                        if(this.n2 == this.n3){
                            this.Pregunta = '2 de estos numeros son el mismo'
                        }
                    else{
                          this.Pregunta ='Todos los numero son diferentes';
                          }
                    }
                    else if(contador == 3){
                        this.Pregunta = 'Todos los numero son iguales';

                    }
                    else{
                        this.Pregunta= '2 de estos numeros son el mismo';
                    }
                    }

   
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
    button{
        border-radius: 50px;
        border: 2px solid #ea0e0e;
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