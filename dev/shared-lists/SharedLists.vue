<template>
  <hr />
  <h2>Shared lists</h2>
  <div class="shared-list-container">
    <div class="list">
      <VueSortableJs v-model:list="demoList" :options="sortableOptions">
        <template #item="{ element, index }">
          <div class="list-item">{{ element }} {{ index }}</div>
        </template>
      </VueSortableJs>
    </div>

    <div class="list">
      <VueSortableJs v-model:list="demoList" :options="sortableOptions">
        <template #item="{ element, index }">
          <div class="list-item-shared">{{ element }} {{ index }}</div>
        </template>
      </VueSortableJs>
    </div>
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
      group: "shared",
      animation: 150,
    });

    const code = `
        <VueSortableJs v-model:list="demoList" :options="sortableOptions">
          <template #item="{ element, index }">
            <div class="list-item">{{ element }} {{ index }}</div>
          </template>
        </VueSortableJs>

        <VueSortableJs v-model:list="demoList" :options="sortableOptions">
          <template #item="{ element, index }">
            <div class="list-item-shared">{{ element }} {{ index }}</div>
          </template>
        </VueSortableJs>
        
        export default {
          components: {
            VueSortableJs,
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
