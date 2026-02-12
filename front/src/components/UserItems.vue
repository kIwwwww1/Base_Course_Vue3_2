<template>
    <div class='new_users'>
        <button @click="delete_user(user_id)">Удалить</button>
        <p id="user_name">{{user.name}}</p>
        <p id="user_password">{{user.password}}</p>
        <p id="user_email">{{user.email}}</p>
    </div>
</template>

<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        },
        user_id: {
            type: Number,
            required: true
        },
        delete_user: {
            type: Function,
            required: true
        }
    },
    data() {
        return {

        }
    },
    methods() {
        
    }
}
</script>

<style scoped>

.new_users button {
  width: 100px;
  height: 30px;
  align-self: flex-end;
  margin: 5px 0px;
  background-color: rgb(235, 44, 44);
  cursor: pointer;
  border-style: none;
  color: rgb(255, 255, 255);
  border-radius: 6px;
}

</style>