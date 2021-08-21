# vue-sortable-js
[![npm version](https://badge.fury.io/js/vue3-sortable-js.svg)](https://badge.fury.io/js/vue3-sortable-js)

This library is a wrapper for SortableJs ![](https://github.com/SortableJS/Sortable)

## Install
```bash
npm i --save vue3-sortable-js

yarn add vue3-sortable-js
```

## Simple List
![](https://media2.giphy.com/media/fU6Q5PSbLZysLlaP2b/giphy.gif)

<details>
  <summary>See more</summary>
  
  ```vue
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
  </script>
  ```
</details>

## Shared Lists
![](https://media4.giphy.com/media/Fb4EtdvaqgpR98caym/giphy.gif)

<details>
  <summary>See more</summary>
  
  ```vue
  <VueSortableJs v-model:list="demoList" :options="sortableOptions">
    <template #item="{ element, index }">
      <div class="list-item">{{ element }} {{ index }}</div>
    </template>
  </VueSortableJs>

  <VueSortableJs v-model:list="demoList" :options="sortableOptions">
    <template #item="{ element, index }">
      <div class="list-item-extra">{{ element }} {{ index }}</div>
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
        group: 'shared',
        animation: 150,
      });

      return { demoList, sortableOptions };
    },
  };
  </script>
  ```
</details>
