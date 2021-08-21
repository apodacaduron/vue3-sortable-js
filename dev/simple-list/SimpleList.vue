<template>
  <hr />
  <h2>Simple list</h2>
  <div class="list">
    <VueSortableJs v-model:list="demoList" :options="sortableOptions">
      <template #item="{ element, index }">
        <div class="list-item">{{ element }} {{ index }}</div>
      </template>
    </VueSortableJs>
  </div>
  <details>
    <summary>Show options</summary>
    <pre><code>{{ code }}</code></pre>
  </details>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import VueSortableJs from "@/vue-sortable-js.vue";

export default defineComponent({
  components: {
    VueSortableJs,
  },
  setup() {
    const demoList = ref(["Vue", "Sortable", "Plugin"]);

    const sortableOptions = ref({
      animation: 150,
    });

    const code = `
      <VueSortableJs v-model:list="demoList" :options="sortableOptions">
        <template #item="{ element, index }">
          <div class="list-item">{{ element }} {{ index }}</div>
        </template>
      </VueSortableJs>

      <script>
      export default {
        components: {
          VueSortableJs,
        },
        setup() {
          const demoList = ref(["Vue", "Sortable", "Plugin"]);

          const sortableOptions = ref({
            animation: 150,
          });

          return { demoList, sortableOptions };
        },
      };
    `;

    return { demoList, sortableOptions, code };
  },
});
</script>
