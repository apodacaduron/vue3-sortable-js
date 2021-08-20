<template>
  <div ref="sortableElement" :class="containerClass">
    <div v-for="(item, index) in list" :key="index" :class="itemClass">
      <slot name="item" :element="item" :index="index" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, PropType, ref, watchEffect } from "vue";
import Sortable, { Swap, MultiDrag } from "sortablejs";

Sortable.mount(new Swap(), new MultiDrag());

export default defineComponent({
  name: "Draggable",
  inheritAttrs: false,
  props: {
    containerClass: {
      type: String,
      default: "sortable-container",
    },
    itemClass: {
      type: String,
      default: "sortable-item",
    },
    list: {
      type: Array,
      default: () => [],
    },
    options: {
      type: Object as PropType<Sortable.Options>,
    },
  },
  emits: ["update:list"],
  setup(props) {
    const sortableElement = ref<HTMLUListElement>();
    const sortable = ref<Sortable>();

    onMounted(() => {
      if (!sortableElement.value) return;
      sortable.value = Sortable.create(sortableElement.value, props.options);
    });

    watchEffect(() => {
      sortable.value?.option("disabled", props.options?.disabled);
    });

    return {
      sortableElement,
    };
  },
});
</script>