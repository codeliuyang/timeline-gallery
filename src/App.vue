<template>
  <div id="app">
    <TimelineBoard msg="Welcome to Your Vue.js App" />
    <modal name="hello-image" @before-open="beforeOpen" height="auto" draggable=".modal-image" :resizable="true">
      <img class="modal-image" :src="imgUrl" />
    </modal>
  </div>
</template>

<script>
import TimelineBoard from './components/TimelineBoard.vue'

export default {
  name: 'App',
  components: {
    TimelineBoard
  },
  data() {
    return {
      imgUrl: ''
    }
  },
  methods: {
    beforeOpen(event) {
      console.log(event.params.imgUrl)
      this.imgUrl = event.params.imgUrl
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 10% 0 10%;
}

.modal-image {
  width: 100%;
  height: 100%;
  cursor: pointer;
}
</style>
