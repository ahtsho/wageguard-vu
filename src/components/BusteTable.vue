<template>
  <EasyDataTable
    :headers="headers"
    :items="items"
  />
</template>
<script lang="ts">
import { defineComponent } from "vue";
import type { Header, Item } from "vue3-easy-data-table";

export default defineComponent({
  setup() {
    const headers: Header[] = [
    {text:"Id", value:"id"},  
    {text:"Mese", value:"mese",sortable: true}, 
    {text:"Anno", value:"anno",sortable: true},   
    {text:"Competenze", value:"totaleCompetenze",sortable: true}, 
    {text:"Arrotondamento", value:"arrotondamento"}, 
    {text:"Netto", value:"nettoDelMese"}
    ];

    const items: Item[] = [];

    return {
      headers,
      items
    };
  },
});
fetch('api/busta/list')
  .then(res => res.json())
  .then(res => console.log(res));
</script>