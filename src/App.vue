<template>
  <input type="text" v-model="userName" placeholder="Title">
  <input type="text" v-model="userPass" placeholder="Content">
  <input type="text" v-model="userOpis" placeholder="Opis">
  <p className="error">{{ error }}</p>
  <button @click="sendData()">Отправить</button>
  <h1>Список статей</h1>

  <User v-for="(el, index) in users" :key="index" :user="el" :index="index" :deleteUser="deleteUser"/>
  

</template>

<script>
import User from './components/User.vue'

export default {
  components: { User },
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      userPass: '',
      userOpis: ''
    }
  },
  methods: {
      sendData() {
        if(this.userName == '') {
          this.error = 'Ошибка: 000';
            return;
        } else  if(this.userPass == '') {
          this.error = 'Ошибка: 001';
          return;
        } else  if(this.userOpis == '') {
          this.error = 'Ошибка: 002';
          return;
        } 

        

        this.error = '';

        this.users.push({
          name: this.userName,
          pass: this.userPass,
          opis: this.userOpis,
        })
      },
      deleteUser(index) {
        this.users.splice(index, 1)
      }
  }

}
</script>

<style scoped>
input {
  display: block;
  margin-bottom: 10px;
  border-radius: 15px;
  border: 1px solid sienna;
  text-align: center;
  outline: none;
  padding: 10px 100px;
  background: floralwhite;
  color: #333;
}

button {
  border: 0;
  border-radius: 20px;
  outline: none;
  padding: 10px 15px;
  background: rebeccapurple;
  color: bisque;
  font-weight: bold;
  cursor: pointer;
  transition: transform 300ms ease;
}

button:hover {
    transform: translateY(-3px);
}

.user {
  width: 300px;
  margin-top: 20px;
  border: 1px solid sienna;
  background: rgb(202, 202, 202);
  color: #000000;
  padding: 20px;
  border-radius: 5px;
}
</style>
