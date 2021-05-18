<template>
  <div>
    <p>{{this.giveyou}}</p>
    <button @click="sendmessage">親にデータ渡すボタン</button>
  </div>
</template>

<script>
  import Vue from 'vue'

  export default Vue.extend({
    name: 'HelloWorld',

    data: () => ({
      messagekoi:'こい'
    }),
    props:{
      'giveyou':{
        type: String
      }
    },
    methods:{
      sendmessage(){
        this.$emit('catchmessage',this.messagekoi)
      }
    },

  })
</script>
