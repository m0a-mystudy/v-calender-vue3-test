<template>
  <DatePickerWarp :v-model="range"/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import DatePickerWarp from './components/datePickerWarp.vue';

interface Range {
  start: Date | null,
  end: Date | null,
}
const dummyAPI = (): Promise<Range>  => {
      return new Promise(resolve => {setTimeout(() => {
        resolve({
            start: new Date('2012-10-01'),
            end: new Date('2022-11-01'),
          })
      }, 500)});
}

export default defineComponent({
  name: 'App',
  components: {
    DatePickerWarp
  },
  data() {
    return {range :{start: null, end: null} as Range}
  },
  async mounted(){
    this.range = await dummyAPI();
  },
});
</script>
