<template>
  <div>
    <box-form @create-new-box="addBox($event)"></box-form>
    <box-card 
      v-for="(item, index) in listOfBox"
      :key="index"
      :box="item"
      :new-box="listOfBox[index]">
    </box-card>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'




export default Vue.extend({
    // components: { boxCard, Form  },
    name: "IndexPage",
    // components: { Form, boxCard },
    data() {
      return{
       
        listOfBox: [{
          title:"Boxes",
          selected: 'cotton',
          weight: '7kg',
          technology: ['isPerishable'],
          msg: 'labas'
        }]
      }
    },
     methods: {
  addBox: function(theNewBox: any) {
    console.log(theNewBox, 'newBox')
    this.listOfBox.unshift(theNewBox);
  }
}
})
</script>
