<template>
  <hr />
  <h2>Simple list</h2>
  <div class="list">
    <VueSortablejs v-model:list="demoList" :options="sortableOptions">
      <template #item="{ element, index }">
        <div class="list-item">{{ element }} {{ index }}</div>
      </template>
    </VueSortablejs>
  </div>
  <details>
    <summary>Show options</summary>
    <pre><code>{{ code }}</code></pre>
  </details>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import VueSortablejs from "@/vue-sortablejs.vue";

export default defineComponent({
  components: {
    VueSortablejs,
  },
  setup() {
    const demoList = ref(["Vue", "Sortable", "Plugin"]);

    const sortableOptions = ref({
      animation: 150,
    });

    const code = `
        <VueSortablejs v-model:list="demoList" :options="sortableOptions">
          <template #item="{ element, index }">
            <div class="list-item">{{ element }} {{ index }}</div>
          </template>
        </VueSortablejs>
        
        export default {
          components: {
            VueSortablejs,
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
