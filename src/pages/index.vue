<template>
  <div>
    <todo-form @handleParentAddTodo="handleParentAddTodo"/>
    <todo-list
      :todos="todos"
      @handleParentDeleteTodo="handleParentDeleteTodo"
      @handleParentCompleteTodo="handleParentCompleteTodo"
    />
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm'
import TodoList from '@/components/TodoList'

export default {
  name: 'Todo',
  components: {
    TodoForm,
    TodoList
  },
  data () {
    return {
      todos: []
    }
  },
  mounted () {
    // json がぶっ壊れている可能性があるので、その場合は local storage を削除
    if (localStorage.getItem('todos')) {
      try {
        this.todos = JSON.parse(localStorage.getItem('todos'))
      } catch (e) {
        localStorage.removeItem('todos')
      }
    }
  },
  methods: {
    handleParentAddTodo (value) {
      if (value) {
        this.todos.unshift({text: value, complete: false})
        const parsed = JSON.stringify(this.todos)
        localStorage.setItem('todos', parsed)
      }
    },
    handleParentDeleteTodo (index) {
      this.todos.splice(index, 1)
      this.saveTodos()
    },
    saveTodos () {
      // this.todos の値を保存
      const parsed = JSON.stringify(this.todos)
      localStorage.setItem('todos', parsed)
    },
    handleParentCompleteTodo (index) {
      this.todos[index].complete = !this.todos[index].complete
    }
  }
}
</script>

<style scoped>

</style>
