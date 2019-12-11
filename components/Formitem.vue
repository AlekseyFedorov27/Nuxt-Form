<template>
<v-app>
  <v-form
    ref="form">
      <v-select
      v-model="select" 
      :items="itemsSELECT"
      label="Item"

    ></v-select> 

<div  v-for="(i, ind) in INPUTname.inputArr" :key="ind">
    <v-text-field
      v-model="INPUTname.inputArr[ind].nametip"
      :label="INPUTname.iputname"
    ></v-text-field>
</div>


    <v-btn
      color="warning"
      @click="addInputArr">
      Добавить {{INPUTname.iputname}}
    </v-btn>

       <v-btn
      color="warning"
      @click="delInputArr()">
      Удалить {{INPUTname.iputname}}
    </v-btn>

  </v-form> 
  </v-app>
</template>
<script>
  export default {
    props: ['submitForm'],
    data: () => ({
      itemsSELECT:[],
      select: 'Возраст респондента',
      items: [
        {name :'Возраст респондента', iputname: "Диапазон", inputArr:[{ nametip:''}] },
        {name :'Тип карты лояльности', iputname: "Тип", inputArr:[{nametip:''}]},
        {name :'Статус карты лояльности', iputname: "Статус", inputArr:[{nametip:''}]},
      ],
    }),
    created(){
      this.items.forEach((item, i, arr)=> {
        this.itemsSELECT.push(item.name)
      });
    },
    computed:{
       INPUTname(){
         return this.items.find((item)=> item.name == this.select );
      },
    },
     watch: {
      submitForm(){
        if (this.submitForm){
        this.$emit('calling', this.INPUTname);
        }
      }
     },
    methods: {
      addInputArr(){        
        this.INPUTname.inputArr.push({ nametip:''})
      },
      delInputArr(){
        this.INPUTname.inputArr.splice(-1, 1)
      },

    },
  }
</script>
<style >
.v-application--wrap{
      min-height: 10vh!important;
      margin-bottom: 30px;
}
</style>