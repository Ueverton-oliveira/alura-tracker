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
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <div>
           <Cronometro  />
          </div>

          <div class="iniciar">
            <button class="button" @click="iniciar">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
              <span>play</span>
            </button>
          </div>
          <div class="finalizar">
            <button class="button" @click="finalizar">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
              <span>stop</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Cronometro from "@/components/Cronometro.vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Formulation",
  components: {
    Cronometro
  },
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0
    }
  },
  methods: {
    iniciar () {
      this.cronometro =  setInterval(() => {
        this.tempoEmSegundos += 1
      }, 1000)
    },
    finalizar () {
      clearInterval(this.cronometro)
    }
  }
});
</script>

<style scoped>
.iniciar {
  position: relative;
  right: 20px;
}
</style>