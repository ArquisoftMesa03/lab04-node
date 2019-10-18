<template>
        <div id="app">
          <p>Nombre del curso</p>
          <input type="text" v-model="courseName" placeholder="Course Name">
          <p>El mensaje is: {{ courseName }}</p>
          <p>Creditos</p>
          <input type="text" v-model="credits" placeholder="Credits">
          <p>El mensaje is: {{ credits }}</p>
          <p></p>
          <button v-on:click="createREST()">Crear con REST</button>
          <button v-on:click="createGraphQL()">Crear con GraphQL</button>
        </div>
</template>

<script>

import axios from 'axios'

    export default {
        props: {
            courseName: String,
            credits: String,
            responseData: String
        },
        methods: {
            createREST: function () {
                
                var config = {headers: {'Access-Control-Allow-Origin': '*'}};
                
                axios.post('http://3.230.92.44:3000/courses-ms/resources/courses',{name: this.courseName,credits: this.credits},config)
                .then(response => 
                this.responseData = response.data,
                alert('Creado con REST!' + '\n' + this.responseData)
                )
                .catch(error =>
                {alert(error)});
                
            },
            createGraphQL: function () {
                alert('Creado con Graphql!')
            }
        },  
    };
</script>