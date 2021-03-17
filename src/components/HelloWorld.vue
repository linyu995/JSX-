<template>
 <div>
   <div>{{state.name}}</div><!--
     <div>测试</div>-->
     <Demo></Demo>
 </div>
</template>

<script>
import {defineComponent,reactive,onMounted,defineAsyncComponent} from 'vue'
/*import Demo from '../util/demo'*/ /*方法一*/

const demo=defineComponent({
   components:{
       /*Demo*/ /*方法一*/
       Demo:defineAsyncComponent(()=>import('../util/demo.jsx'))   /*方法二*/
   } ,
   setup(){
     const state=reactive({
          name:'话语'
      })
     onMounted(()=>{
         state.name='张飞'
     })
      return {
         state,name
      }
  },
})
export default demo

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
