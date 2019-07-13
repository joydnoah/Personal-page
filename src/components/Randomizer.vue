<template>
  <div class="base-content">
    {{ msg }}
    <div>
      <button @click="randomize('randomizer')">Randomize!</button>
    </div>
    <div v-for="random in random_list">
      <div>{{ random }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Randomizer',
  data () {
    return {
      msg: 'Randomizer',
      random_list: []
    }
  },
  methods: {
    randomize () {
      console.log(this.random_list)
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
<style scoped>
</style>
