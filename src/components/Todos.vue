<template>
  <div>
    <div  v-bind:key='todo.id' v-for='todo in todos'>
      <TodoItem v-bind:todo="todo" v-on:del-todo='deleteTodo'/> 
    </div>
  </div>
  
</template>

<script>
  import TodoItem from './TodoItem'
  export default  {
    name: 'Todos',
    props: ['todos'],
    components: {
      TodoItem
    },
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      deleteTodo(id) {
        this.$emit('del-todo', id)
      }
    },
    computed: {

    }
}


</script>

<style scoped>
  .todos {

  }
</style>
