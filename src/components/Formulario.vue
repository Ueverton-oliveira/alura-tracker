<template>
  <div class="box">
    <div class="columns">
      <div class="columns is-8" role="form" aria-label="Formulário para criação de nova tarefa">
        <input
            type="text"
            class="input"
            placeholder="Qual tarefa você deseja iniciar?"
            v-model="descricao"
        />
      </div>
      <div class="columns">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from "@/components/Temporizador.vue";
export default {
  name: 'Formulario',
  components: {
    Temporizador
  },
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido: number) :void {
      console.log('tempo da tarefa', tempoDecorrido)
      console.log('descriçaõ da tarefa', this.descricao)
      this.descricao = ''
    }
  }
}

</script>

<style scoped>
.iniciar {
  position: relative;
  right: 20px;
}
</style>