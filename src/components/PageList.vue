<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'PageList',
    props: {
      pages: {
        type: Array,
      },
    },
  });
</script>
