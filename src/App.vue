
<template>
  <div id="app">
    <HeaderItem header="hehe" />
    <TodosVue description='Haluya' name='Ky' address="An Giang"  />
  </div>
</template>

<!-- filename: HeaderItem.vue -->
<script>
import HeaderItem from './components/Header';
import TodosVue from './components/Todos';
export default {
  name: 'App',
  components: {
    HeaderItem,
    TodosVue
  },
 
}


</script>

<style>
.myApp {
  color: red;
}
</style>