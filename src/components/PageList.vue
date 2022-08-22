<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'PageList',
    props: {
      pages: {
        type: Array,
      },
      currentPage: {
        type: Number,
      },
    },
    methods: {
      // Change the current page based on index.
      changePage(index: any) {
        this.$emit('change-page', index);
      },

      // Add a new page to the list of pages.
      addPage() {
        this.$emit('add-page');
      },
    },
  });
</script>

<template>
  <div class="page-list">
    <ul>
      <li
        v-for="(page, index) of pages"
        class="page"
        v-bind:class="{ active: index === currentPage }"
        @click="changePage(index)"
        v-bind:key="index"
      >
        <div>
          {{ page.title }}
        </div>
      </li>
      <div class="btn">
        <button class="add-page" @click="addPage()">New Page</button>
      </div>
    </ul>
  </div>
</template>

<style scoped lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap');

  $bg-color: #faedcd;
  $border-color: #d4a373;
  $border-color-alt: #ba7f44;
  $main: #ccd5ae;
  $alt: #e9edc9;
  $list: #edede9;
  $list-border: #d6ccc2;
  $font: 'Space Mono', monospace;

  .page-list {
    width: 500px;
    padding: 10px;
  }

  ul {
    list-style-type: none;
    padding: 0;
    margin: 10px;
  }

  li {
    max-width: 500px;
    padding: 1rem;
    font-size: 1.25rem;
    min-height: 1.5rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    border: 2px solid $list-border;
    margin-bottom: 10px;
    background-color: $list;
  }

  li:hover {
    cursor: pointer;
    background-color: $main;
  }

  .active {
    background-color: $main;
  }

  .active:hover {
    background-color: $alt;
  }

  .add-page {
    cursor: pointer;
  }

  .btn {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }

  button {
    border-style: none;
    padding: 10px;
    background-color: $border-color;
    margin-right: 15px;
    border-radius: 5px;
    color: white;
    font-size: 15px;
    font-family: $font;
    cursor: pointer;
    transform: translateY(-3px);
    transition: transform 0.1s ease;
  }

  button:hover {
    background-color: $border-color-alt;
    transform: translateY(-5px);
  }

  button:active {
    transform: translateY(0);
  }
</style>
