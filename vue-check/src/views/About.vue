<template>
  <div class="about">
    <div v-for="i in state">
    <router-link :to="'/detail/'+i.id">
    <Item :content="i" />
    </router-link>
    </div>
  </div>
</template>
<script>
import Item from './Item.vue'
  export default {
    data(){
      return {
        state:[]
      }
    },
    components:{
      Item
    },
   watch:{
     '$route'(){
       this.$http.post('http://localhost:3000',{fenlei:this.$route.params.fenlei},{emulateJSON:true}).then(e=>this.state=e.body)
     }
   },
    created(){
      this.$http.post('http://localhost:3000',{fenlei:this.$route.params.fenlei},{emulateJSON:true}).then(e=>this.state=e.body)
    }
  }
</script>
