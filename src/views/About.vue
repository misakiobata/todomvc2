<template>
  <div class="about">
    <p>done</p>
    <todo :all="tall" @catchmessage2="displaymessage"></todo>
    <div v-for="(todo,index) in todos" :key="index">
      <input type="checkbox">
      {{todo}}
      <v-btn
          @click="deletetodo(index)"
          type="button"
          color="purple"
      >
        消去
      </v-btn>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Todo from "@/components/todo.vue";
export default Vue.extend({
  name: 'Home',
  data: () => ({
    givemessage:'all',
    tall:true,
    todos:[],
  }),
  components: {
    Todo,
  },
  props: {

  },
  methods: {
    displaymessage(message){
      this.todos.push(message)
    },
    deletetodo: function(index){
      this.todos.splice(index,1)
    }
  },

})
</script>