<template>
<div>
  <div>
   <input class="item" v-model="inputValue"/>
   <button @click="handleSubmit">提交</button>
  </div>
  <ul>
  <todoitem
  v-for="(item, index) of list"
  :key="index"
  :content="item"
  :index="index"
  @delete="handleDelete"
  ></todoitem>
  </ul>
</div>
</template>

<script>
import todoitem from './components/todoitem'

export default {
  components: {
    'todo-item':todoitem
  },
  data () {
    return {
      inputValue:'',
      list:[]
    }
  },
  methods:{
    handleSubmit (){
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
      handleDelete (index){
        this.list.splice(index, 1)
      }
    }
}
</script>

<style>

</style>
