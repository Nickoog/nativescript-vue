<template>
  <GridLayout columns="200, *">
    <Button col="0" @tap="toggle" :text="statusText"></Button>
    <Label col="1" :text="groceryItem.name"></Label>
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
