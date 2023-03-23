<template>
  <div class="block list">
    <div
        v-for="item in oneList"
        :key="item.id"
        @click="$emit('selectOne', item)"
        class="item"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'OneList',
  props: ['oneList']
}
</script>
