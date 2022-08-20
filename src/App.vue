<template>
  <PageView />
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import PageView from './components/PageView.vue';

  export default defineComponent({
    name: 'App',
    components: {
      PageView,
    },
  });
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&display=swap');

  $font: 'Caveat', cursive, Helvetica, Arial, sans-serif;
  $bg-color: #faedcd;
  $border-color: #d4a373;
  $border-color-alt: #ba7f44;
  $main: #ccd5ae;
  $alt: #e9edc9;

  #app {
    box-sizing: border-box;
    font-family: $font;
  }
</style>
