# vue-sortable-js

## Install
```bash
npm i --save vue3-sortable-js

yarn add vue3-sortable-js
```

## Simple List
![](https://giphy.com/embed/fU6Q5PSbLZysLlaP2b)

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
