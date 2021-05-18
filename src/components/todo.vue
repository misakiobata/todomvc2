<template>
  <v-container>
  <v-card  outlined>
    <v-card-title>
      todolist
    </v-card-title>
    <v-row no-gutters>
      <v-col>

        <v-col>
        <v-text-field
          label="予定表"
          hint="ここに入力してください"
          @keydown.enter="onClick"
          v-model="message"
        >
        </v-text-field>
        </v-col>
        <v-btn
            @click="onClick"
            type="button"
            color="blue"
            v-bind:disabled="isempty"
        >
          追加
        </v-btn>

      </v-col>
    </v-row>
    <v-divider/>
    <div v-if="all">
      <div  v-for="(todo,index) in todos"
           :key="index" >
          <input
            type="checkbox"
          >
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
    <div v-if="!all">
      <p>あいう</p>
    </div>

  </v-card>

  </v-container>
</template>

<script>

export default {
  name: "todo",
  data: () => ({
    message:'',
    todos:[
      'asd','sdf'
    ],

  }),
  methods:{
    onClick: function(){
      this.todos.push(this.message)
      this.$emit('catchmessage2',this.message)
    },
    deletetodo: function(index){
      this.todos.splice(index,1)
    }
  },
  computed:{
    isempty: function(){
      if(this.message == '') return true;
      else                   return false;
    },

  },
  props:{
    'all':{
      type: Boolean
    }
  }


}
</script>

<style scoped>

</style>