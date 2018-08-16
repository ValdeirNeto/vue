<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Nome">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Horário">{{ item.hours }}</md-table-cell>
        <md-table-cell md-label="Ação"> 
        <md-button class="md-just-icon md-simple md-primary">
            <md-icon>check</md-icon>
            <md-tooltip md-direction="top">Consulta Realizada</md-tooltip>
          </md-button>
          <md-button class="md-just-icon md-simple md-danger">
            <md-icon>close</md-icon>
            <md-tooltip md-direction="top">Cancelar</md-tooltip>
          </md-button>
        </md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: 'ordered-table',
  props: {
    tableHeaderColor: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      selected: [],
      users: [
        {
          id: 1,
          name: 'Dakota Rice',
          hours: '12:00',
          action: 'Oud-Turnhout'
        },
        {
          id: 2,
          name: 'Minerva Hooper',
          hours: 'Curaçao',
          action: 'Sinaai-Waas'
        },
        {
          id: 3,
          name: 'Sage Rodriguez',
          hours: 'Netherlands',
          action: 'Overland Park'
        },
        {
          id: 4,
          name: 'Philip Chaney',
          hours: 'Korea, South',
          action: 'Gloucester'
        }
      ]
    }
  }
}
</script>
