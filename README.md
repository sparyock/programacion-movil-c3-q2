# programacion-movil-c3-q2

<template>
  <ion-item lines="none">
    <ion-label>{{ label }}</ion-label>
    <ion-input 
      :type="type" 
      :placeholder="placeholder" 
      v-model="inputValue"
    ></ion-input>
  </ion-item>
</template>

<script>
import { IonItem, IonLabel, IonInput } from '@ionic/vue';

export default {
  name: 'CustomInput',
  components: {
    IonItem,
    IonLabel,
    IonInput,
  },
  props: {
    label: {
      type: String,
      default: 'Label'
    },
    type: {
      type: String,
      default: 'text'
    },
    placeholder: {
      type: String,
      default: 'Enter value...'
    },
    inputValue: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
ion-item {
  margin: 10px 0;
}
</style>
