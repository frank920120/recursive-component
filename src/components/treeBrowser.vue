<template>
  <div class="contaner">
    <div :style="{ 'margin-left': `${depth * 20}px` }">
      <h3>
        <span @click="handleClick" v-if="hasChildren">{{
          expanded ? "-" : "+"
        }}</span
        >{{ roots.title }}
      </h3>
      <template v-if="expanded">
        <treeBrowser
          v-for="(node, index) in roots.children"
          :roots="node"
          :depth="depth + 1"
          :key="index"
        />
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: "treeBrowser",
  props: {
    roots: Object,
    depth: {
      default: 0,
      type: Number,
    },
  },
  data() {
    return { expanded: false };
  },
  computed: {
    hasChildren() {
      return this.roots.children;
    },
  },
  methods: {
    handleClick() {
      if (this.hasChildren) {
        this.expanded = !this.expanded;
      }
    },
  },
};
</script>

<style lang="stylus" scoped></style>
