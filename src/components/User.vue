<template>
     <div className="user"> 
      <h3>{{ user.name }}</h3>
      <p>{{ user.pass }}-<b>{{ user.opis }}</b> </p>
      <button @click="deleteUser(index)">Delete</button>
  </div>
</template>

<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        },
        index: {
            type: Number,
            required: true
        },
        deleteUser: {
            type: Function,
            required:true
        }
    }

}
</script>

<style scoped>
 
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
</style>
