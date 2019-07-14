<template>
  <div class="main-block">
    <ul>
      <li><a href="default.asp">{{ msg }}</a></li>
    </ul>
    <div class="randomizer-content">
      <button class="button" @click="randomize('randomizer')">Randomize!</button>
      <div class="result-list" v-for="random in random_list">
        <div>{{ random }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Randomizer',
  data () {
    return {
      msg: 'Teamfight Tactics Randomizer',
      random_list: []
    }
  },
  methods: {
    randomize () {
      var list_of_classes = ['Caballeros', 'Guardianes', 'Pistoleros', 'Peleadores', 'Cambiaformas', 'Espadachines', 'Elementalistas', 'Cazadores', 'Hechiceros', 'Asesinos'];
      var list_of_origins = ['Pirata', 'Robot', 'Vacio', 'Yordle', 'Demonio', 'Noble', 'Fantasma', 'Salvaje', 'Dragon', 'Exilio', 'Ninja', 'Glacial', 'Imperial'];
      var random_class = Math.floor(Math.random() * 10);
      var random_origin = Math.floor(Math.random() * 13);
      this.random_list.push(list_of_classes[random_class] + " - " + list_of_origins[random_origin]);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
body {
  background: url("https://d1v0ze4r2jabid.cloudfront.net/energy.jpg") no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  margin: 0;
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #010a12;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

/* Change the link color to #111 (black) on hover */
li a:hover {
  background-color: #111;
}
.button {
  background-color: #e7e7e7;
  color: black;
  border: none;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
} /* Gray */
.randomizer-content {
  padding-left: 15%;
  padding-top: 2%;
  color: white;
}
.result-list{
  padding-top: 10pt;
}
</style>
