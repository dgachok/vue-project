<template>
  <div>
    <li v-for="item in list"
        v-bind:key="item.id">1{{item.text}}</li>
   </div>
</template>

<script>
export default {
  name: 'List',
  props: {
    list: Array
  },
   created: function () {
      console.log('value list: ' + this.list)
    }
}
</script>

<style scoped>
</style>
