<template>
  <Page>
    <StackLayout>
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
    toggle() {
      this.groceryItem.done = !this.groceryItem.done
    }
  }
}
</script>
