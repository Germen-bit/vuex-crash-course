<template>
  <div>
    <h3>AddTodo</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="Add todo...">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    ...mapActions(['addTodo']),
    onSubmit(e) {
      e.preventDefault()

      this.addTodo(this.title)
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 10px;
  outline: 0;
  border: 1px solid #41b883;
}

input[type="submit"] {
  flex: 2;
  color: #fff;
  cursor: pointer;
  border: 1px solid #41b883;
  background: #41b883;
}

</style>