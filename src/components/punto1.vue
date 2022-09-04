<template>
      <div>
        <h1>Punto 1:</h1>
        <h2>Ingresa los segundos que vas a trasformar en S,M,H:</h2>
          <input type="number" v-model="question" placeholder="Ingresa los segundos" @keypress.enter="Calcular()"/>
      </div>
      <br>
  <div>
      <h2>{{question}}</h2>
      <label>Horas: {{Hora}}  </label>
      <br>
      <label>Minutos: {{Minutos}}</label>
      <br>
      <label>Segundos: {{sobrante2}}</label>
  </div>
  </template>
  <script>

  export default {
      data(){
          return{
              question: '',
                Hora: '', Minutos:'', sobrante2: ''
              
  
          }
      },
      methods:{
          Calcular(){
            this.Hora = this.question / 3600,
            this.sobrante1 = this.question % 3600,
            this.Minutos = this.sobrante1 / 60,
            this.sobrante2 = this.sobrante1 % 60
              

            
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