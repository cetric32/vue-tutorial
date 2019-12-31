<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <Items :lists='lists' :remove="remove" ></Items>
  </div>
</template>

<script>
import Items from './Items.vue'

export default {
  name: 'Home',
  data () {
    return {
      lists: [
        { 'name': 'cetric' },
        { 'name': 'azuatech' },
        { 'name': 'vuejs' },
        { 'name': 'Angular' },
        { 'name': 'Pikachu' }
      ],
      newItem: null
    }
  },
  props: {
    msg: String
  },
  methods: {
    remove (index) {
      this.lists.splice(index, 1)
    },
    addItem () {
      this.lists.push({ 'name': this.newItem })
      this.newItem = null
    }
  },
  components: {
    Items
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
