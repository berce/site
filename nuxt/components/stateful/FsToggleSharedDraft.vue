<template>
  <v-switch v-model="isShared" @change="update"></v-switch>
</template>

<script>
export default {
  name: 'FsToggleShareDraft',
  props: {
    shared: {
      type: Boolean,
      required: true
    },
    draft: {
      type: String,
      required: true
    }
  },
  methods: {
    update() {
      const { data } = this.$fs.updateDraft(this.draft, {shared: this.isShared})
    }
  },
  data() {
    return {
      isShared: this.shared
    }
  }
}
</script>
