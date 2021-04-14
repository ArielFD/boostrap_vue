<template>
  <div class="mt-5">
    <b-row class="mt-5">
      <b-col cols="12" md="12">
        <h1>Formulario</h1>
      </b-col>
      <b-col cols="12" md="6">
        <b-form-input
          v-model="number"
          type="number"
          placeholder="Enter your number"
          :state="comprobarNumero"
        ></b-form-input>
        <small>My age</small>
        <div class="mt-2">Value: {{ number }}</div>
      </b-col>
      <b-col cols="12" md="6">
        <b-form-input
          v-model="text"
          type="text"
          placeholder="Enter your text"
          :state="comprobarTexto"
        ></b-form-input>
        <small>My name</small>
        <div class="mt-2">Value: {{ text }}</div>
      </b-col>
      <b-col class="md-3">
          <b-form-select v-model="selected" :options="animales"></b-form-select>
          <p>{{selected}}</p>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      text: "",
      number: 0,
      selected:null,
      animales:[
          {value:null,text: 'Please select an option'},
          { value: 'a', text: 'This is First option' },
          { value: 'b', text: 'This is second option' },
          { value: 'c', text: 'This is thirds option' }
      ]
    };
  },
  computed:{
      comprobarTexto(){
          return this.text.match("Ariel")?true:false
      },
      comprobarNumero(){
          return this.number==29?true:false
      }
  }
};
</script>