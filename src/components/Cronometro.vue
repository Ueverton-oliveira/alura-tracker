<template>
  <section>
    <strong>
      {{ tempoDeCorrido }}
    </strong>
  </section>
</template>

<script lang="ts">
import { defineComponet } from 'vue'
export default defineComponet ({
  name: "Cronometro",
  props: {
    tempoEmSegundos: {
      type: Number,
      default: 0

    }
  },
  computed: {
    tempoDeCorrido () : string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substring(11,8)
    }
  },
})
</script>


<style scoped>

</style>