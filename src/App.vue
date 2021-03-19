<template>
  <div id="holder">
    <nav>
      <button @click="changeView('Toto')">Totoro</button>
      <button @click="changeView('Dino')">Dino</button>
    </nav>
    <component v-bind:is="view" />
  </div>

</template>

<script>
import { defineComponent } from 'vue'
import Toto from './components/Toto.vue'
import Dino from './components/Dino.vue'
export default defineComponent({
  name: 'App',
  data() {
    return {
      view: 'Toto'
    }
  },
  methods: {
    changeView(to) {
      this.view = to
    }
  },
  components: {
    Toto,
    Dino
  }
})
</script>

<style lang="scss">
body{
  margin: 0;
}
#holder{
  width: 100vw;
  height: 100vh;
  display: grid;
}
nav {
  width: 100%;
  display: flex;
  justify-content: space-around;
  height: 40px;
}
</style>
