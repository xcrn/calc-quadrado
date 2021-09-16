<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Calcular quadrado</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Calculadora de Quadrado</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">
        <form @submit.prevent="calculo">
          <div>
              <label>Calcular o quadrado do número: </label>
          </div>
          <input v-model.number="num1"/>
           <ion-button v-on:click="calculo" type="submit">Calcular</ion-button>
        </form>
        <div>
          <p><strong>Resultado: {{ resultadoFinal }} </strong></p>
        </div>
      </div>

    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';

export default {
  name: 'App',
  data () {
    return {
      num1: 0,
      resultadoFinal: 0
    }
  },

  methods: {
   calculo () {
    const { num1, resultadoFinal }= this;
    this.resultadoFinal = (num1 * num1);
  }
},
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar
  }
};
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);

}

form {
  border: 1px solid #8c8c8c;
  border-radius: 3px;
  margin: 0 35% 1%;
  padding: 25px;
}

input {
  margin: 5px;
  width: 80px;
  height: 40px;
  border: 0px;
  border-bottom: 1px solid #8c8c8c;
}

button {
  background-color: blue;
  color: aliceblue;
  width: 100px;
  font-size: 14px;
  padding: 5px 0;
  border-radius: 3px;
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>