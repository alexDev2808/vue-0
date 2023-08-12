<template>
  <nav class="navbar">
    <img src="./assets/logo.svg" width="50"/>
    <h3>Todo List App</h3>
  </nav>

  <main class="container">
    <section>
      <form class="add-todo-form">
        <input type="text" placeholder="Todo Title" />
        <div>
          <button>Add ToDo</button>
        </div>
      </form>
    </section>
    <section>
      <div class="todo">
        <p>Pasear al perro</p>
        <div>
          <button class="remove-todo-btn">&times;</button>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>

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
