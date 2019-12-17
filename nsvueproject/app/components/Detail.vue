<template>
  <Page>
    <StackLayout>
      <Button text="Go back" @tap="onBackTap"></Button>
      <Label :text="groceryItem.name"></Label>
      <Button :text="statusText" @tap="toggle"></Button>
    </StackLayout>
  </Page>
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
    onBackTap() {
      this.$navigateBack()
    },
    toggle() {
      this.groceryItem.done = !this.groceryItem.done
    }
  }
}
</script>
