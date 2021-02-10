<template>
  <div>
    <b-container class="mt-2 nes-container is-dark with-title is-centered m-auto" style="padding: 1rem;">
      <p class="title">todo list for today</p>
      <div :key="index" v-for="(todo, index) in todos">
        <b-row class="d-flex" align-h="between" style="align-items: center">
          <div class="text-left w-75 overflow-auto">
            <label style="margin-bottom: 0">
              <input @click="handleCompleteTodo(index)" type="checkbox" class="nes-checkbox is-dark"/>
              <span>{{ todo.text }}</span>
            </label>
          </div>
          <div class="text-right w-25">
            <button type="button" class="nes-btn is-error mr-3" style="font-size: 8px" @click="handleDeleteTodo(index)">delete</button>
          </div>
        </b-row>
      </div>
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['todos'],
  methods: {
    handleDeleteTodo (index) {
      this.$emit('handleParentDeleteTodo', index)
    },
    handleCompleteTodo (index) {
      this.$emit('handleParentCompleteTodo', index)
    }
  }
}
</script>

<style scoped>
  /* .line {
    text-decoration: line-through;
  } */
</style>
