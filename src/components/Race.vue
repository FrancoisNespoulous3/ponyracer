<template>
  <div>
    <h2>{{ raceModel.name }}</h2>
    <p>{{ fromNow(raceModel.startInstant) }}</p>
    <ul v-for="pony in raceModel.ponies" :key="pony.id">
      <li>{{ pony.name }}</li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { RaceModel } from '@/models/RaceModel';
import fromNow from '@/utils/FromNow';

export default defineComponent({
  name: 'Race',

  props: {
    raceModel: {
      type: Object as PropType<RaceModel>,
      required: true
    }
  },

  setup() {
    return {
      fromNow
    };
  }
});
</script>
