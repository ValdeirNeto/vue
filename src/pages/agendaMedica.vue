<template>
  <form>
    <md-card>
      <md-card-header data-background-color="blue">
        <h4 class="title">Adicionar Agenda</h4>
        <p class="category">Adicione sua Agenda</p>
      </md-card-header>
      <md-card-content>
        <div>
          <div class="md-layout" v-for="(livre, index) in horarios">
            <div class="md-layout-item md-small-size-100 md-size-20">
              <md-field>
                <label>Data</label>
                <md-input v-model="data" type="date"></md-input>
              </md-field>
            </div>
            <div class="md-layout-item md-small-size-100 md-size-20 text-right" v-for="horas in livre.hours">
              <md-field>
                <label>Horario</label>
                <md-input v-model="hours" type="text"></md-input>
              </md-field>
            </div>
              <div class="md-layout-item md-small-size-100">
                  <md-button class="btn-fab" @click="horas(index)">+</md-button>
            </div>
          </div>
            <div class="md-layout-item md-size-100 text-left">
              <md-button @click="addAgenda" class="md-raised md-success">Mais Dias livres</md-button>
            </div>
            <div class="md-layout">
            <div class="md-layout-item md-small-size-100 md-size-85 text-right">
              <md-button class="md-raised md-darger">Cancelar</md-button>
            </div>
            <div class="md-layout-item md-small-size-100 md-size-10 text-right">
              <md-button class="md-raised md-success">Gravar</md-button>
            </div>
          </div>
        </div>
      </md-card-content>
    </md-card>
  </form>
</template>

<script>
export default {
  data () {
    return {
      horarios: [
        {
          data: '',
          hours: ['']
        }
      ]
    }
  },
  methods: {
    addAgenda () {
      this.horarios.push({
        data: '',
        hours: ['']
      })
    },
    horas (index) {
      this.horarios[index].hours.push({
        hours: null
      })
    }
  }
}
</script>
<style>
</style>
