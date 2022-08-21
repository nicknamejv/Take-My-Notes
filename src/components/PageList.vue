<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'PageList',
    props: {
      pages: {
        type: Array,
      },
      activePage: {
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
        v-bind:class="{ active: index === activePage }"
        @click="changePage(index)"
        v-bind:key="index"
      >
        <div>
          {{ page.title }}
        </div>
      </li>
      <button class="new-page" @click="newPage()">New Page</button>
    </ul>
  </div>
</template>
