<template>
  <div id="app">
    <div class="container">
      <img
        class="logo"
        src="http://sortablejs.github.io/Sortable/st/og-image.png"
        alt="logo"
      />
      <h1>Vue-Sortable-Js Features</h1>
      <SimpleList />
      <SharedLists />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import VueSortableJs from "@/vue-sortable-js.vue";
import SimpleList from "./simple-list/SimpleList.vue";
import SharedLists from "./shared-lists/SharedLists.vue";

export default defineComponent({
  name: "ServeDev",
  components: {
    VueSortableJs,
    SimpleList,
    SharedLists,
  },
});
</script>

<style>
body {
  font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif,
    "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";

  background: #d8e3fa;
}
hr {
  height: 1px;
  background-color: #e4e4e4;
  border: none;
}
.container {
  max-width: 900px;
  margin: 0 auto;
  background: white;
  padding: 1rem;
  border-radius: 1rem;
}
.logo {
  margin: 0 auto;
  height: 128px;
  width: auto;
  display: block;
}
.shared-list-container {
  display: flex;
  flex-direction: row;
  gap: 1rem;
}
.list {
  width: 100%;
  background: white;
  padding: 1rem;
  box-sizing: border-box;
  border: 1px solid #e4e4e4;
  border-radius: 1rem;
}
.list-item {
  padding: 1rem;
}
.list-item-shared {
  padding: 1rem;
  background: rgb(171, 171, 245);
}
.list-item:hover {
  background: #e2e2e2;
  border-radius: 1rem;
}
details {
  padding: 1rem;
}
</style>