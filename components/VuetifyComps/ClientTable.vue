<template>
  <v-card>
    <v-card-title>
      <img src="~/assets/Logo2.png" width="100px">
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-table-search"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="clients"
      :search="search"
     
    >
      <template slot="items" slot-scope="props">
        <tr @click="props.expanded = !props.expanded">
          <td>{{ props.item.last_name }}, {{ props.item.first_name }}</td>
          <td class="text-xs-right">{{ props.item.house }}</td>
          <td class="text-xs-right">{{ props.item.house_mgr }}</td>
          <td class="text-xs-right">{{ props.item.client_id }}</td>
        </tr>
      </template>
      <v-alert slot="no-results" :value="true" color="error" icon="warning">
        Your search for "{{ search }}" found no results.
      </v-alert>
      <template slot="expand" slot-scope="props">
        <v-layout v-for="med in meds" v-bind:key="med.id" v-if="props.item.client_id == med.client_id" >     
           
           
  
CT NAME: {{ med.ct_name }} - ID: {{ med.client_id }}

  </v-layout>
</template>

    </v-data-table>
  </v-card>
</template>
<script>
  import db from '~/components/firebaseInit'
  export default {
    name: 'ClientTable',
    data() {
      return {
        headers: [{
            search: '',
            text: 'First Name',
            align: 'left',
            sortable: true,
                  value: 'first_name'
          },
          {
            text: 'House',
            align: 'right',
                  value: 'house'
          },
          {
            text: 'House Manager',
            align: 'right',
                  value: 'house_mgr'
          },
          {
            text: 'Client ID',
            align: 'right',
                  value: 'client_id'
          }
        ],
        meds: [],
        clients: []
      }
    },
    //get med collection    
    created() {
      db.collection('meds').get().then(querySnapshot => {
        querySnapshot.forEach(doc => {
          const data = {
            'id': doc.id,
            'med_id': doc.data().med_id,
            'client_id': doc.data().client_id,
            'ct_name': doc.data().ct_name,
            'script_num': doc.data().script_num,
            'med_gen_name': doc.data().med_gen_name,
            'med_brand_name': doc.data().med_brand_name,
            'count_initial': doc.data().count_initial,
            'count_timestamp': doc.data().count_timestamp,
            'fill_date': doc.data().fill_date
          }
          this.meds.push(data)
        })
      })
      //--get clients collection
      db.collection('clients').get().then(querySnapshot => {
        querySnapshot.forEach(doc => {
          const data = {
            'id': doc.id,
            'client_id': doc.data().client_id,
            'med_id': doc.data().med_id,
            'first_name': doc.data().first_name,
            'last_name': doc.data().last_name,
            'house': doc.data().house,
            'house_mgr': doc.data().house_mgr
          }
          this.clients.push(data)
        })
      })
    }
  }
</script>