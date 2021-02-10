<template>
  <div>
    <b-container class="mb-5">
      <b-row class="nes-field is-inline d-flex">
        <input v-model="value" type="text" id="dark_field" class="nes-input is-dark w-75" placeholder="what to do...">
        <button @click="handleAddTodo" type="button" class="nes-btn is-warning w-25">add</button>
      </b-row>

      <!-- <b-input-group>
        <b-form-input type="text" v-model="value"/>
        <b-input-group-append>
          <b-button variant="info" @click="handleAddTodo">submit</b-button>
        </b-input-group-append>
      </b-input-group> -->
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'TodoForm',
  data () {
    return {
      value: ''
    }
  },
  methods: {
    handleAddTodo () {
      this.$emit('handleParentAddTodo', this.value)
      this.value = ''
    }
  }
}
</script>

<style scoped>

</style>
