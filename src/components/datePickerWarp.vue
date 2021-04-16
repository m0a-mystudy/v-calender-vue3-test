<template>
  <v-date-picker  
    :modelValue="modelValue"
    @update:modelValue="$emit('update:modelValue', $event)"
    mode="dateTime" is24hr is-range
  >
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
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'DatePickerWarp',
  props: {
    modelValue: {
      type: Object,
      required: false,
    },
  },
  emits: ['update:modelValue'],
});
</script>
