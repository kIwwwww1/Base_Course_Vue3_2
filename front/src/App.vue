<template>

  <h3>{{ info }}</h3>
  <p>{{ msg }}</p>
  <div class="main_div">
    <button type="button" @click="user_data()" class="button">Отправит #1</button>
    <button type="button" @mouseenter="user_data2()" class="button">Отправить #2</button>
    <p id="_couner">{{ counter }}</p>
  </div>

</template>

<script>

export default {
  data() {
    return {
      info: 'Hello World #1',
      msg: 'Hello World #2',
      counter: 0,
    }
  },
  methods: {
    user_data() {
      this.info = 'Новая кнопка #1'
      this.counter += 1
      console.log('Hello World #1')
      console.log(`Счетчик: ${this.counter}`)
    },
    user_data2() {
      this.msg = 'Новая кнопка #2'
      console.log('Hello World #2')
    }
  }
}

</script>

<style scoped>

* {
  display: flex;
  padding: 0px;
  margin: 0px;
}

h3 {
  font-weight: lighter;
}

p {
  color: rgb(156, 156, 219);
}

.main_div {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
}

.button {
  padding: 10px 20px;
  margin: 10px;
  border: 1px solid #42b983;
  border-radius: 5px;
  background-color: #42b983;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
}

#_couner {
  padding: 10px 15px;
  margin: 20px;
  font-size: 5em;
}

</style>
