<!-- We don't really put any stuff into App.vue, it's basically a container for the other components -->
<!-- although ultimately it is still just a component, but its the root -->
<template>
  <div id="app">
    <DogButton/>
    <CatButton/>
    <DisplaySelection/>
  </div>
</template>

<script>
import DisplaySelection from '@/components/DisplaySelection.vue';
import DogButton from '@/components/DogButton.vue';
import CatButton from '@/components/CatButton.vue';

export default {
  name: 'App',
  components: {
    DisplaySelection,
    DogButton,
    CatButton
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
