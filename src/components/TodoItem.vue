<template>
  <div>
    <input type="checkbox" :id="id" :checked="isCompleted">
    <label :for="id">{{text}}</label>
  </div>
</template>
<script>
export default {
  props: {
    text: {required: true, type: String},
    completed: {required: true, type: Boolean},
    id: {required: true, type: String}
  },
  data() {
    return{
      isCompleted: this.completed
    }
  }
}
</script>
<style scoped>

</style>