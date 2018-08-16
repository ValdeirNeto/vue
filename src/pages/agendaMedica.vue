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
              <div class="md-small-size-100">
                  <md-button class="md-just-icon md-green" @click="horas(index)">
                    <md-icon>add</md-icon>
                  </md-button>
            </div>
            <md-button class="md-just-icon md-danger" @click="delhoras(index)">
               <md-icon>close</md-icon>
          </md-button>
          </div>
          <div class="md-layout">
            <div class="md-layout-item md-small-size-100 md-size-16 text-left">
              <md-button @click="addAgenda" class="md-raised md-success">Mais Dias livres</md-button>
            </div>
             <div class="md-layout-item md-small-size-100 md-size-80 text-left">
              <md-button @click="removeAgenda" class="md-raised md-danger">Remover Dia</md-button>
            </div>
          </div>
            <div class="md-layout">
            <div class="md-layout-item md-small-size-100 md-size-85 text-right">
              <md-button class="md-raised md-danger">Cancelar</md-button>
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
    removeAgenda () {
      this.horarios.pop({
        data: '',
        hours: ['']
      })
    },
    horas (index) {
      this.horarios[index].hours.push({
        hours: null
      })
    },
    delhoras (index) {
      this.horarios[index].hours.pop({
        hours: null
      })
    }
  }
}
</script>
<style>
</style>