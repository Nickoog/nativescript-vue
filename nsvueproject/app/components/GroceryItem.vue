<template>
  <GridLayout columns="200, *">
    <Label col="0" :text="statusText"></Label>
    <Label col="1" class="item-name" :text="groceryItem.name"></Label>
  </GridLayout>
</template>

<script>
export default {
  props: ['groceryItem'],
  data() {
    return {}
  },
  computed: {
    statusText() {
      return this.groceryItem.done ? 'Done' : 'Not Done'
    }
  },
  methods: {
    toggle() {
      this.$emit('toggleDone', this.groceryItem)
    }
  }
}
</script>

<style lang="scss" scoped>
page {
  label {
    color: red;
  }
  .line-through {
    text-decoration: line-through;
  }
}
.item-name {
  animation-name: show;
  animation-duration: 0.6s;
  animation-fill-mode: forwards;
}
@keyframes show {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>

<style lang="scss">
label {
  background-color: gray;
}
</style>
