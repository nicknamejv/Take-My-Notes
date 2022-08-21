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
  $bg-color: #faedcd;
  $border-color: #d4a373;
  $border-color-alt: #ba7f44;
  $main: #ccd5ae;
  $alt: #e9edc9;
  $list: #edede9;
  $list-border: #d6ccc2;

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
    max-width: 350px;
    padding: 1rem;
    font-size: 1.25rem;
    min-height: 1.5rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    border: 2px solid $list-border;
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
    margin-top: 10px;
  }

  button {
    border-style: none;
    padding: 10px;
    background-color: $border-color;
    margin-right: 15px;
    border-radius: 5px;
    color: white;
    font-size: 15px;
    cursor: pointer;
  }

  button:hover {
    background-color: $border-color-alt;
  }

  .page {
    background-color: $list;
  }
</style>
