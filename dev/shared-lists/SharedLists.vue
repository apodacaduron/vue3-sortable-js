<template>
  <hr />
  <h2>Shared lists</h2>
  <div class="shared-list-container">
    <div class="list">
      <VueSortablejs v-model:list="demoList" :options="sortableOptions">
        <template #item="{ element, index }">
          <div class="list-item">{{ element }} {{ index }}</div>
        </template>
      </VueSortablejs>
    </div>

    <div class="list">
      <VueSortablejs v-model:list="demoList" :options="sortableOptions">
        <template #item="{ element, index }">
          <div class="list-item-shared">{{ element }} {{ index }}</div>
        </template>
      </VueSortablejs>
    </div>
  </div>

  <details>
    <summary>Show options</summary>
    <pre><code>{{ code }}</code></pre>
  </details>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import VueSortablejs from "@/vue-sortable-js.vue";

export default defineComponent({
  components: {
    VueSortablejs,
  },
  setup() {
    const demoList = ref(["Vue", "Sortable", "Plugin"]);

    const sortableOptions = ref({
      group: "shared",
      animation: 150,
    });

    const code = `
        <VueSortablejs v-model:list="demoList" :options="sortableOptions">
          <template #item="{ element, index }">
            <div class="list-item">{{ element }} {{ index }}</div>
          </template>
        </VueSortablejs>

        <VueSortablejs v-model:list="demoList" :options="sortableOptions">
          <template #item="{ element, index }">
            <div class="list-item-shared">{{ element }} {{ index }}</div>
          </template>
        </VueSortablejs>
        
        export default {
          components: {
            VueSortablejs,
          },
          setup() {
            const demoList = ref(["Vue", "Sortable", "Plugin"]);

            const sortableOptions = ref({
              group: "shared",
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
