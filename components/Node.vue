<template>
  <div class="leaf">
    <a-icon type="credit-card" v-if="!leaf.children" />
    <a-icon v-else type="caret-right"></a-icon>
    <span>{{ leaf.name }} : {{ leaf.type }}</span>

    <div v-if="leaf.children && leaf.children.length">
      <Node v-for="(child,key) in leaf.children" :key="key" :leaf="child" />
    </div>
  </div>
</template>
<script>
export default {
  name: 'NuxtNode',
  props: ["leaf"],
}
</script>
<style scoped>
.leaf {
  margin-left: 1em;
}
</style>