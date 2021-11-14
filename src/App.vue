<template>
  <div
    id="app"
    :class="counter % 2 === 0 ? 'bg-pink' : 'bg-white'"
  >
    <h1>
      Combien d'oreillers dans votre vie ?
    </h1>
    <img
      :src="require(`./assets/coussins/${counter}.png`)"
      :alt="`Coussin N°${counter}`"
    >
    <div class="actions-container">
      <div
        class="substract"
        @click="substract"
        :style="counter > 1 ? '' : 'visibility: hidden' "
      >
        <font-awesome-icon icon="minus" />
      </div>
      {{ counter }}
      <div
        class="add"
        @click="add"
        :style="counter < 10 ? '' : 'visibility: hidden' "
      >
        <font-awesome-icon icon="plus" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      counter: 1
    }
  },
  methods: {
    substract () {
      this.counter--
    },
    add () {
      this.counter++
    }
  }
}
</script>

<style scoped>
#app {
  margin: -8px;
  padding: 0 1rem;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: space-between;
  height: 100vh;
  font-size: 16px;
  color: orangered;
  font-weight: 700;
}
#app.bg-white {
  background-color: white;
}
#app.bg-pink {
  background-color: pink;
}
h1 {
  text-align: center;
  margin-top: 4rem;
  font-size: 2rem;
}
.actions-container {
  display: flex;
  justify-content: center;
  padding: 0 2rem;
  margin-bottom: 2rem;
  font-size: 2rem;
}
.actions-container .substract,
.actions-container .add {
  margin: 0 2rem;
  background-color: white;
  border: 2px solid orangered;
  border-radius: 100%;
  width: 32px;
  height: 32px;
  display: flex;
  justify-content: center;
  align-content: center;
  padding: .25rem;
}
</style>
