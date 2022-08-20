<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'PageView',
  });
</script>

<template>
  <div class="page">
    <div>
      <label for="page-title">Title</label>
      <input
        type="text"
        class="page-title"
        name="page-title"
        placeholder="Enter a title!"
      />
      <label for="page-content">Content</label>
      <textarea
        class="page-content"
        name="page-content"
        placeholder="Take down some notes!"
      ></textarea>
      <div class="btn-footer">
        <button>Delete Page</button>
        <button>Save Page</button>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  $bg-color: #faedcd;
  $border-color: #d4a373;
  $border-color-alt: #ba7f44;
  $main: #ccd5ae;
  $alt: #e9edc9;

  .page {
    width: 100vw;
    height: 100vh;
    padding: 35px;
    background-color: $bg-color;
  }

  .title {
    text-align: center;
    width: 500px;
    padding: 10px;
    margin: 0 auto;
    color: $main;
    border: 5px $border-color solid;
  }

  .page-content,
  .page-title {
    border-style: none;
    border-radius: 5px;
    border: solid 3px $border-color;
    width: 100%;
    box-sizing: border-box;
    margin-bottom: 25px;
  }

  label {
    margin-bottom: 10px;
    display: inline-block;
    color: $main;
    font-weight: bolder;
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

  input,
  textarea {
    padding: 10px;
  }
</style>
