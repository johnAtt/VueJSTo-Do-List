<template>
  <div id="app">
    <h1>To-Do List</h1>
    <toDolist/>
  </div>
</template>
 


<script>

import toDolist from './components/toDolist'


export default {
  name: 'App',
  components: {
    toDolist
  }
}
</script>

<style >
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');
@font-face {
  font-family: bebas;
  src: url(./assets/font/BebasNeue-Regular.otf);
}
body {
  background-image: url("https://i.pinimg.com/originals/19/fc/21/19fc21dc1f8a339ea8f302c75320a28f.jpg");
  background-position: center;
  background-size: cover;
  font-family: bebas;
  display: grid;
  grid-template-rows: auto;
  justify-items: center;
}
body, html {
  margin: 0;
  height: 100%;
}
#app {
    width: 50%;
    border: 3px solid black;
    margin:30px;
    border-radius:20px;
}
h1{
  font-family: bebas;
  font-size:60px;
  color:blue;
  margin:0;
}
</style>
