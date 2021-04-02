  <template>
  <div id="totoHolder" @click="playSqueak()">
    <transition name="fade">
      <h1 v-if="message !== ''">{{ message }}</h1>
    </transition>
    <img src="../assets/img/pusheen.gif" alt="pusheen" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0,
      message: "",
    };
  },
  methods: {
    playSqueak() {
      this.counter++;
      const url = this.getSound("meow.mp3");
      const squeak = new Audio(url);
      squeak.play();
      this.checkTimes();
    },
    getSound(sound) {
      return require(`../assets/sounds/${sound}`);
    },
    checkTimes() {
      switch (this.counter) {
        default:
          this.message = "";
          break;
        case 2:
          this.message = "I'm sorry I keep hurting you :(";
          break;
        case 4:
          this.message = "I hope Mr. Pusheen makes you smile";
          break;
        case 6:
          this.message = "god the sound gets annoying after a couple times";
          break;

        case 100:
          this.message = "really?? you hit it 100 times???";
          break;
      }
    },
  },
};
</script>
<style scoped lang="scss">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
#totoHolder {
  height: 60vh;
  width: 50vh;
  place-self: center;
  transition: 0.3s;
  display: grid;
  &:active {
    transform: scale(0.95) rotate(2deg);
  }
  h1 {
    grid-area: 1/1/1/1;
    align-self: start;
    justify-self: center;
    transform: translateY(-13vh);
    font-family: sans-serif;
    text-align: center;
  }
  #toto {
    grid-area: 1/1/1/1;
    height: 100%;
    place-self: center;
  }
  #heartsvg {
    grid-area: 1/1/1/1;
    height: 40px;
    width: 40px;
    align-self: start;
    justify-self: start;
    margin: 6vh 0 0 6vh;
    fill: red;
    animation: pulse alternate infinite 1s;
  }
  @keyframes pulse {
    from {
      transform: scale(1);
    }
    to {
      transform: scale(1.5);
    }
  }
}
</style>
