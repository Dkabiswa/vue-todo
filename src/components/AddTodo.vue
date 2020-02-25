<template lang="html">

  <div class="add-todo" v-on:submit.prevent='addTodo'>
    <h1>add-todo Component</h1>
    <form>
      <input type='text' v-model='title' name='title' placeholder='add todo' />
      <input type='submit' value='submit' class='btn' />
    </form>
  </div>

</template>

<script lang="js">

  export default  {
    name: 'AddTodo',
    props: [],
    mounted () {

    },
    data () {
      return {
        title: ''
      }
    },
    methods: {
      addTodo() {
        this.$emit('add-todo', {
          title: this.title,
          completed: false
        })
        this.title = ''
      }
    },
    computed: {

    }
}


</script>

<style scoped>
  form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
</style>
