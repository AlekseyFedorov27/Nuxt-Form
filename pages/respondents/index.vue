<template>
  <div>
    <div>Добавить опрос</div>
      <Formitem  @calling='submitForm' :submitForm="childState" v-on:submitForm="lockChild"
       v-for="(item, index) in items" :key="index"/>

    <v-btn  @click="add" >
      Нажмите чтобы добавить новое условие
    </v-btn>

    <v-btn  @click="permitChild" >
      Отправить форму
    </v-btn>


  </div>
</template>
<script>
import Formitem from '~/components/Formitem'

export default {
  components: {
    Formitem
  },
   data: () => ({
     childState: false,
     items: [
     { id: '1'},
     ]
   }),
   methods: {
    lockChild: function () {
      this.childState = false;
    },
    permitChild: function () {
      this.childState = true;
    },
     add(){
       this.items.push({id: Math.random()*10})
     },
     submitForm(post){
        console.log('Отправка формы', post);
     }
   }
}
</script>