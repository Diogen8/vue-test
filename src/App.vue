<template>
  <div class="container">
    <div class="header">
      Post trucks
    </div>
    <div class="top-table">
      <div class="top-table__controls-wrapper">
        <div class="top-table__control">play</div>
        <div class="top-table__control">new</div>
        <div class="top-table__control">delete</div>
        <div class="top-table__control">repost</div>
      </div>
      <div class="top-table__header">
        <div
          class="top-table__header-item"
          v-for="(value,key) in top_table.fields"
          :key="key+'_'+value"
        >{{value}}</div>
      </div>
    </div>
    <modal></modal>
  </div>
</template>

<script>

import modal from './components/Modal'

export default {
  name: 'App',
  components: {
    modal
  },
  data: function () {
    return {
      top_table: {
        fields: [
          'Call Control',
          'Read',
          'Sound / Auto Call',
          'Truck',
          'Origin',
          'Destination',
          'Pickup',
          'DH-O',
          'DH-D',
          'F/P',
          'Length',
          'Weight',
          'Trip',
          'Alarm',
          'Actions'
        ]
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .top-table {
    display: flex;
    flex-direction: column;

    &__controls-wrapper {
      display: flex;
    }

    &__control {
      display: flex;
      justify-content: center;
      margin: 0 10px;
      width: 150px;
      background-color: black;
      color: white;
    }

    &__header {
      display: flex;
      margin-top: 20px;
    }

    &__header-item {
      flex-basis: calc(100% / 15);
      flex-grow: 1;
      padding: 8px 0;
      background-color: black;
      color: white;
      text-align: center;
      border-left: 1px solid #dfdfdf;
      border-right: 1px solid #dfdfdf;
    }
  }
</style>
