<template>
  <div class="box">
    <div class="columns">
      <div class="columns is-8" role="form" aria-label="Formulário para criação de nova tarefa">
        <input
            type="text"
            class="input"
            placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <div class="columns">
        <Temporizador />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from "@/components/Temporizador.vue";
export default {
  name: 'Formulario',
  components: {Temporizador}
}

</script>

<style scoped>
.iniciar {
  position: relative;
  right: 20px;
}
</style>