<template>
  <div class="few-selected block">
    <div
        v-if="fewSelected.length"
        class="list"
    >
      <div
          v-for="item in fewSelected"
          :key="item.id"
          @click="$emit('deleteItem', item)"
          class="item"
      >
        {{ item.name }}
      </div>
    </div>

    <p>selected: {{ selected || 'not selected' }}</p>
  </div>
</template>

<script>
export default {
  name: 'FewSelected',
  props: ['fewSelected'],
  computed: {
    selected() {
      return this.fewSelected?.map((item) => item.name).join(' / ')
    }
  }
}
</script>

<style lang="scss">
.few-selected {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
</style>
