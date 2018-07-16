<template>
  <div id="app">
    <h3>This is a test</h3>
    <multi-select
      v-model="values"
      search
      :options="options"
      :btnLabel="btnLabel"
      :selectOptions="data" />
  </div>
</template>

<script>
import multiSelect from 'vue-multi-select';
import 'vue-multi-select/dist/lib/vue-multi-select.min.css';

export default {
  name: 'App',
  data() {
    return {
      btnLabel: 'A simple vue multi select',
      name: 'first group',
      values: [
        { label: '2' },
        { label: '3' },
      ],
      reloadInit: false,
      data: [{
        title: 'part one',
        elements: [
          { label: '0', disabled: true },
          { label: '2' },
          { label: '3' },
          { label: '8' },
          { label: '9' },
          { label: '11' },
          { label: '13' },
          { label: '14' },
          { label: '15' },
          { label: '18' },
        ],
      }, {
        title: 'part two',
        elements: [
          { label: '23' },
          { label: '25' },
          { label: '31' },
          { label: '42' },
          { label: '56' },
          { label: '76' },
          { label: '82' },
          { label: '42' },
          { label: '13' },
          { label: '21' },
        ],
      }],
      options: {
        multi: true,
        groups: true,
        labelName: 'label',
        labelList: 'elements',
        groupName: 'title',
        cssSelected: option => (option.selected ? { 'background-color': '#5764c6' } : ''),
      },
    };
  },
  methods: {
    reloadFunction() {
      this.values = [
        { label: '2' },
        { label: '3' },
      ];
      this.reloadInit = true;
    },
  },
  components: {
    multiSelect,
  },
};
</script>

<style lang="scss" src="./main.scss"></style>
