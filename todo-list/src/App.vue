<template>
  <nav class="navbar">
    <img src="./assets/logo.svg" width="50"/>
    <h3>Todo List App</h3>
  </nav>

  <main class="container">
    <section>
      <form class="add-todo-form">
        <input v-model="todoTitle" type="text" placeholder="Todo Title" />
        <div>
          <button @click.prevent="addTodo">Add ToDo</button>
        </div>
      </form>
    </section>
    <section>
      <div v-for="todo in todos" class="todo" :key="todo.id">
        <p>{{ todo.title }}</p>
        <div>
          <button @click="removeTodo(todo)" class="remove-todo-btn">&times;</button>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
  export default {
    data() {
      return {
        todoTitle: "",
        todos: []
      }
    },
    methods: {
      addTodo() {
        this.todos = this.todos.concat([{
          id: Math.floor(Math.random() * 1000),
          title: this.todoTitle,
        }])
      },

      removeTodo(todoTitle) {
        this.todos = this.todos.filter(todo => todo !== todoTitle);
      }
    }
  }
</script>


<style scoped>
.navbar {
  display: flex;
  align-items: center;
  background-color: var(--navbar-color);
  padding: 20px;
}
.add-todo-form {
  display: flex;
  justify-content: space-between;
}
.add-todo-form input {
  width: 70%;
  border: solid 2px var(--accent-color);
  padding-left: 20px;

}
.add-todo-form button {
  background-color: var(--accent-color);
  color: var(--text-color);
  border: none;
  height: 50px;
  padding: 0 24px;
}

.todo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--accent-color);
  margin-top: 30px;
  padding: 0 20px;
  border-radius: 8px;
}
.remove-todo-btn {
  border-radius: 50%;
  border: none;
  height: 40px;
  width: 40px;
  font-size: 32px;
  color: var(--text-color);
  background-color: var(--danger-color);
}
</style>
