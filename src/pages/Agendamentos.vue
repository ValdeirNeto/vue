<template>
  <div class="content">
   <div class="md-layout-item md-large-size-100 md-xsmall-size-100 md-size-50">
        <md-card>
          <md-card-header data-background-color="blue">
            <h4 class="title">Consultas do Dia</h4>
            <p class="category">{{ data }}</p>
          </md-card-header>
          <md-card-content>
            <ordered-table table-header-color="dark"></ordered-table>
          </md-card-content>
        </md-card>
      </div>
    </div>
</template>

<script>
import {
  SimpleTable,
  OrderedTable
} from '@/components'

export default{
  components: {
    OrderedTable,
    SimpleTable
  }
}
</script>
