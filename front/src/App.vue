<template>
  <div class="reg_div">
    <input type="text" v-model="user_name" placeholder="Имя">
    <input type="password" v-model="user_password" placeholder="Пароль">
    <input type="email" v-model="user_email" placeholder="Email">
    <button @click="add_user">Отправить</button>
  </div>

  <div v-if="users.length == 0" class='new_users'>
    <p>Пользователи не найдены</p>
  </div>
  <div v-else-if="users.length == 5" class='new_users'>
    <p>Превышен лимит пользователей</p>
  </div>
  <div v-else class='new_users'>
    <p>Все условия не верны, работает v-else</p>
  </div>

  <UserItems v-for="(user, user_id) in users" :key="user_id" :user="user" :user_id="user_id" :delete_user="delete_user"/>

</template>

<script>

import UserItems from './components/UserItems.vue'

export default {
  components: { UserItems },
  data() {
    return {
      users: [],
      user_name: '',
      user_password: '',
      user_email: '',
    }
  },
  methods: {
    add_user() {
      if (this.user_name == '' || this.user_password == '' || this.user_email == '') {
        window.alert('Заполните все поля')
        return
      }
      this.users.push({
        name: this.user_name,
        password: this.user_password,
        email: this.user_email,
      })
    },
    delete_user(user_id) {
      this.users.splice(user_id, 1)
    }
  }
}

</script>

<style>

* {
  margin: 0px;
  padding: 0px;
}

.reg_div {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px 10px;
}

.reg_div input {
  width: 150px;
  height: 30px;
  padding: 10px 15px;
  border-radius: 7px;
  border: 1px solid black;
  margin: 5px 0px;
}

.reg_div button{
  width: 100px;
  height: 30px;
  margin: 5px 0px;
  background-color: green;
  cursor: pointer;
  border-style: none;
  color: white;
  border-radius: 6px;
}

.new_users {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px 10px;
  background-color: rgb(255, 251, 251);
  width: 300px;
  margin: 10px auto;
  border-radius: 7px;
  border: 3px solid black ;
}

</style>
