<template>
  <div>
      <form @submit.prevent="addItem" >
        <input type="text" v-model="newItem">
        <button type="submit">+ ADD</button>
      </form>
      <ul>
        <li v-for="(item, index) in lists" :key="index">
          {{item.name}}
          <button @click="remove(index)">X</button>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'Items',
  props: {
    lists: Array,
    remove: Function
  },
  methods: {
    addItem () {
      this.lists.push({ 'name': this.newItem })
      this.newItem = null
    }
  }
}
</script>

<style>

</style>
