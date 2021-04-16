<template>
  <v-date-picker v-model="range" mode="dateTime" is24hr is-range>
      <template v-slot="{ inputValue, inputEvents }">
      <input
        :value="inputValue.start"
        v-on="inputEvents.start"
      />
      <input
        :value="inputValue.end"
        v-on="inputEvents.end"
      />
    </template>
    </v-date-picker>
</template>

<script lang="ts">
import { defineComponent, nextTick } from 'vue';

export default defineComponent({
  name: 'App',
  data() {
    return {range :{}}
  },
  mounted(){
    nextTick(() => {
      setTimeout(() => {
        this.range = {
      start: new Date('2012-10-01'),
      end: new Date('2022-11-01')
    }


      }, 5000)


    })
    
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
