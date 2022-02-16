<template>
  <div class="app">
    App.vue
     我是 {{doc.name}}
     今年 {{doc.age}}

     我现在有 {{total}}

    <hr>
    简写--语法糖
    <Child :money.sync="total"/>
    <Child  v-bind.sync="doc"/>
    <hr>
    正常写法
    <!-- <Child :money="total" @update:money="total = $event" /> -->
    <Child :money="total" @update:money="changeTotal($event)" />
    <Child :name="doc.name" :age="doc.age" @update:age="doc.age = $events" />

    <!-- <Child :name="doc.name" :age="doc.age" @update:age="changeAge($event)" /> -->
  </div>
</template>

<script>
import Child from "./Child.vue";
export default {
  data() {
    return { 
      total: 10000,
      doc:{
        name:"zgc",
        age:18
        }
     };
  },
  components: { Child: Child },
  methods:{
    changeTotal(events){
      this.total = events
    },
     changeAge(events){
      this.doc.age = events
    },
  }
};
</script>

<style>
.app {
  border: 3px solid red;
  padding: 10px;
}
</style>