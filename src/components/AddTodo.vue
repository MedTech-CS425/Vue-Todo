<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo">What do you want to do ?</label>
    <input id="new-todo" type="text" name="new-todo" v-model="text" />
    <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  methods: {
    onSubmit () {
      this.text && this.$emit('todo-added', this.text);
    }
  },
  data () {
    return {
      text: ""
    }
  }
};
</script>

<style>
</style>