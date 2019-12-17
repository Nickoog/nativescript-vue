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
    return {
      status: 0
    }
  },
  computed: {
    statusText() {
      return this.status === 0 ? 'Not done' : 'Done'
    }
  },
  methods: {
    toggle() {
      this.status = this.status === 0 ? 1 : 0
    }
  }
}
</script>

