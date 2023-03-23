<template>
  <div id="app">
    <FewSelected :fewSelected="fewSelected" @deleteItem="deleteItem" />
    <OneSelected :oneSelected="oneSelected" @deleteOne="deleteOne" />
    <FewList :fewList="fewList" @selectItem="selectItem" />
    <OneList :oneList="oneList" @selectOne="selectOne" />
  </div>
</template>

<script>
import FewSelected from "@/components/FewSelected";
import OneSelected from "@/components/OneSelected";
import FewList from "@/components/FewList";
import OneList from "@/components/OneList";

export default {
  name: 'App',
  components: {
    FewSelected,
    OneSelected,
    FewList,
    OneList
  },
  data() {
    return {
      fewList: [
        {
          "id": 1,
          "name": "Shoes 1"
        },
        {
          "id": 2,
          "name": "Shoes 2"
        },
        {
          "id": 3,
          "name": "Shoes 3"
        },
        {
          "id": 4,
          "name": "Shoes 4"
        },
        {
          "id": 5,
          "name": "T-shirt 1"
        },
        {
          "id": 6,
          "name": "T-shirt 2"
        },
        {
          "id": 7,
          "name": "T-shirt 3"
        },
        {
          "id": 8,
          "name": "T-shirt 4"
        }
      ],
      oneList: [
        {
          "id": 11,
          "name": "Jacket 1"
        },
        {
          "id": 12,
          "name": "Jacket 2"
        },
        {
          "id": 13,
          "name": "Jacket 3"
        },
        {
          "id": 14,
          "name": "Jacket 4"
        },
        {
          "id": 15,
          "name": "Hoodie 1"
        },
        {
          "id": 16,
          "name": "Hoodie 2"
        },
        {
          "id": 17,
          "name": "Hoodie 3"
        },
        {
          "id": 18,
          "name": "Hoodie 4"
        }
      ],
      fewSelected: [],
      oneSelected: null
    }
  },
  methods: {
    selectOne(item) {
      this.oneSelected = item
    },
    selectItem(item) {
      !this.fewSelected.find(el => el.id === item.id) && this.fewSelected.push(item)
    },
    deleteItem(item) {
      this.fewSelected = this.fewSelected.filter(el => el.id !== item.id)
    },
    deleteOne() {
      this.oneSelected = null
    }
  }
}
</script>

<style lang="scss">
@import "./assets/style.scss";
</style>
