# vue-sortable-js

## Install
```bash
npm i --save vue3-sortable-js

yarn add vue3-sortable-js
```

## Simple List
```vue
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
```