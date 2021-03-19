<template>
    <canvas></canvas>
</template>

<script>
import gsap from 'gsap'
import {Anchor, Box, Illustration, TAU} from 'zdog'
export default {
  methods: {
    
    dinoDance() { 

const HUE = Math.floor(Math.random() * 360)
const COLOR_ONE = `hsl(${HUE}, 100%, 50%)`
const COLOR_TWO = `hsl(${HUE}, 100%, 35%)`
const COLOR_THREE = `hsl(${HUE}, 100%, 15%)`
const COLOR_FOUR = `hsl(${HUE}, 10%, 75%)`

const Scene = new Illustration({
  element: 'canvas',
  dragRotate: true,
  resize: 'fullscreen',
  rotate: {
    y: TAU * 0.065,
    x: TAU * -0.03,
  },
})

const torso = new Box({
  addTo: Scene,
  height: 90,
  width: 70,
  depth: 100,
  stroke: false,
  translate: {
    x: 22,
    y: 0,
    z: 0,
  },
  color: COLOR_ONE,
  leftFace: COLOR_ONE,
  rightFace: COLOR_TWO,
  topFace: COLOR_THREE,
  bottomFace: COLOR_FOUR,
})
const defaultOpts = {
  color: COLOR_ONE,
  depth: 100,
  stroke: false,
  leftFace: COLOR_ONE,
  rightFace: COLOR_TWO,
  topFace: COLOR_THREE,
  bottomFace: COLOR_FOUR,
}

// HEAD
const head = new Anchor({
  addTo: torso,
})

// NECK
new Box({
  ...defaultOpts,
  addTo: head,
  height: 98,
  width: 30,
  translate: {
    x: -8,
    y: -90,
    z: 0,
  },
})

// SCALP
new Box({
  ...defaultOpts,
  addTo: head,
  height: 24,
  width: 110,
  translate: {
    x: 48,
    y: -140,
    z: 0,
  },
})

// SNOUT
new Box({
  ...defaultOpts,
  addTo: head,
  height: 62,
  width: 94,
  translate: {
    x: 72,
    y: -108,
    z: 0,
  },
})

// JAW
new Box({
  ...defaultOpts,
  addTo: head,
  height: 66,
  width: 72,
  translate: {
    x: 13,
    y: -77,
    z: 0,
  },
})

// BOTTOM JAW
new Box({
  ...defaultOpts,
  addTo: head,
  height: 16,
  width: 114,
  translate: {
    x: 36,
    y: -52,
    z: 0,
  },
})

// ARMS
const arm = new Box({
  ...defaultOpts,
  addTo: torso,
  height: 16,
  width: 20,
  depth: 25,
  translate: {
    x: 44,
    y: -11,
    z: -37.5,
  },
})

new Box({
  ...defaultOpts,
  addTo: arm,
  height: 28,
  width: 14,
  depth: 25,
  translate: {
    x: 12,
    y: 6,
  },
})

arm.copyGraph({
  translate: {
    x: 44,
    y: -11,
    z: 37.5,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 102,
  width: 78,
  translate: {
    x: -18,
    y: 16,
    z: 0,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 100,
  width: 86,
  translate: {
    x: -34,
    y: 32,
    z: 0,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 102,
  width: 86,
  translate: {
    x: -50,
    y: 46,
    z: 0,
  },
})

// Tail
new Box({
  ...defaultOpts,
  addTo: torso,
  height: 87,
  width: 96,
  translate: {
    x: -55,
    y: 54,
    z: 0,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 72,
  width: 78,
  translate: {
    x: -80,
    y: 46,
    z: 0,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 72,
  width: 18,
  depth: 80,
  translate: {
    x: -126,
    y: 32,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 72,
  width: 14,
  depth: 60,
  translate: {
    x: -140,
    y: 18,
  },
})

new Box({
  ...defaultOpts,
  addTo: torso,
  height: 88,
  width: 14,
  depth: 40,
  translate: {
    x: -154,
    y: -4,
    z: 0,
  },
})

const leftLeg = new Anchor({
  addTo: torso,
  translate: {
    x: -71,
    y: 103,
    z: 35,
  },
})

new Box({
  ...defaultOpts,
  depth: 30,
  addTo: leftLeg,
  height: 12,
  width: 44,
})

new Box({
  ...defaultOpts,
  addTo: leftLeg,
  height: 15,
  width: 30,
  depth: 30,
  translate: {
    x: -7,
    y: 13,
  },
})

const bottomLeg = new Anchor({
  addTo: leftLeg,
  translate: {
    x: 0,
    y: 0,
  },
})

new Box({
  ...defaultOpts,
  addTo: bottomLeg,
  height: 32,
  width: 16,
  depth: 30,
  translate: {
    x: -14,
    y: 34,
  },
})

new Box({
  ...defaultOpts,
  addTo: bottomLeg,
  height: 16,
  width: 30,
  depth: 30,
  translate: {
    x: -7,
    y: 42,
  },
})

const rightLeg = new Anchor({
  addTo: torso,
  translate: {
    x: -22,
    y: 105,
    z: -30,
  },
})

new Box({
  ...defaultOpts,
  addTo: rightLeg,
  height: 16,
  width: 30,
  depth: 30,
  // color: 'blue'
})

const bottomRightLeg = new Anchor({
  addTo: rightLeg,
  translate: {
    x: 0,
    y: -25,
  },
})

 new Box({
  ...defaultOpts,
  addTo: bottomRightLeg,
  width: 16,
  height: 75,
  depth: 30,
  translate: {
    x: 8,
    y: 10,
  },
})

 new Box({
  ...defaultOpts,
  addTo: bottomRightLeg,
  width: 30,
  height: 16,
  depth: 30,
  translate: {
    x: 15,
    y: 40,
  },
})

gsap.timeline({ repeat: -1, yoyo: true })
  .to(bottomLeg.translate, { duration: 0.1, delay: -0.05, y: -15, ease: 'steps(2)'}, 0)
  .to(bottomRightLeg.translate, { duration: 0.1, y: 0, ease: 'steps(2)'}, 0)

const ALL_CHILDREN = []
const getChildren = item => {
  ALL_CHILDREN.push(item)
  if (item.children) {
    for (const child of item.children) getChildren(child)
  }
}
getChildren(Scene)

const COLOR = {
  H: 0
}
gsap.to(COLOR, { H: 360, repeat: -1, duration: 1, ease: 'none' })
const update = () => {
  const ONE = `hsl(${COLOR.H}, 80%, 50%)`
  const TWO = `hsl(${COLOR.H}, 80%, 35%)`
  const THREE = `hsl(${COLOR.H}, 80%, 15%)`
  const FOUR = `hsl(${COLOR.H}, 10%, 75%)`
  console.log('hello')
  gsap.set(ALL_CHILDREN, {
    color: ONE,
    leftFace: ONE,
    rightFace: TWO,
    topFace: THREE,
    bottomFace: FOUR
  })
  Scene.updateRenderGraph()
  requestAnimationFrame(update)
}

window.Scene = Scene
update()
    },
  },

    mounted() {
      this.dinoDance();
    },
}
</script>

<style scoped lang="scss">
  * {
  box-sizing: border-box;
}
body {
  background: #202124;
  min-height: 100vh;
}
canvas {
  touch-action: none;
    height: 100vh;
    width: 100vw;
}
img {
  position: absolute;
  opacity: 0.2;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>