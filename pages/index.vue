<template>
  <div>
    <Form v-on:create-new-box="addBox($event)"></Form>
    <BoxCard 
    v-for="(item, index) in listOfBox"
    v-bind:key="index"
    :box="item"></BoxCard>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Form from '~/components/Form.vue'
import BoxCard from '~/components/boxCard.vue'

export default Vue.extend({
    name: "IndexPage",
    components: { Form, BoxCard },
    data:function () {
      return{
       
        listOfBox: [{
          title:"Boxes",
          selected: [],
          weight: [],
          technology: [],
          msg: 'labas'
        }]
      }
    },
     methods: {
  addBox: function(theNewBox) {
    this.listOfBox.unshift(theNewBox);
  }
}
})
</script>
