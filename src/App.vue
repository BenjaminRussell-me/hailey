<template>
  <div id="holder">
    <Toto/>
  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Toto from './components/Toto.vue'

export default defineComponent({
  name: 'App',
  components: {
    Toto
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
</style>
