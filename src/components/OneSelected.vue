<template>
  <div class="block list">
    <p>selected: <span @click="$emit('deleteOne')">{{ oneSelected?.name || 'not selected' }}</span></p>
  </div>
</template>

<script>
export default {
  name: 'OneSelected',
  props: ['oneSelected']
}
</script>
