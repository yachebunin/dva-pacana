<template>
  <div class="block list">
    <div
        v-for="item in fewList"
        :key="item.id"
        @click="$emit('selectItem', item)"
        class="item"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'FewList',
  props: ['fewList']
}
</script>
