<template>
  <div class="main">
    <div class="list" v-for="(model, key) in treeModel" :key="key">
      <Node :leaf="model" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      treeModel: [
        {
          name: 'amount',
          type: 'integer',
        },
        {
          name: 'customer',
          type: 'object',
          children: [
            {
              name: 'email',
              type: 'string',
            },
            {
              name: 'phone',
              type: 'string',
            },
            {
              name: 'name',
              type: 'string',
            },
            {
              name: 'ssn',
              type: 'string',
            },
          ],
        },
        {
          name: 'order',
          type: 'object',
          children: [
            {
              name: 'fee',
              type: 'object',
              children: [
                {
                  name: 'amount',
                  type: 'integer',
                },
                {
                  name: 'type',
                  type: 'string',
                },
              ],
            },
            {
              name: 'shipping_address',
              type: 'string',
            },
          ],
        },
      ],
    }
  },
  methods: {
    toggleCollapse(model) {
      model.collpased = !model.collpased
      console.log(model)
      console.log(model.children && model.collpased)
    },
  },
}
</script>
<style lang="css" scoped>
.main {
  margin: 1em;
  padding: 1em;
}

.child-model {
  margin-left: 1em;
}
</style>
