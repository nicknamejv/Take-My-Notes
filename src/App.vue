<template>
  <PageList
    @change-page="changePage"
    @add-page="addPage"
    :pages="pages"
    :currentPage="index"
  />
  <PageView
    @save-page="savePage"
    @delete-page="deletePage"
    :page="pages[index]"
  />
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import PageView from './components/PageView.vue';
  import PageList from './components/PageList.vue';

  export default defineComponent({
    name: 'App',
    components: {
      PageView,
      PageList,
    },
    data() {
      return {
        pages: [],
        index: 0,
      };
    },
    methods: {
      // Add a new page to the list of pages.
      addPage() {
        this.pages.push({
          title: '',
          content: '',
        });
        this.index = this.pages.length - 1;
      },
      // Change the current page.
      changePage(index: any) {
        this.index = index;
      },
      // TODO: Save the current page to the list of pages to localStorage later.
      savePage() {
        console.log('save page');
      },
      // Delete the current page from the list of pages.
      deletePage() {
        this.pages.splice(this.index, 1);
        this.index = 0;
      },
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
