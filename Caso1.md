
# Componente de CRUD con Ionic Vue

## Estructura de Componentes


```vue
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
```

---

## Vista Principal


```vue
<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Formulario de Ejemplo</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Formulario</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="form-container">
        <strong>Completa el formulario:</strong>
        
        <!-- 1. Input de texto -->
        <custom-input label="Nombre" type="text" placeholder="Escribe tu nombre"></custom-input>

        <!-- 2. Input de email -->
        <custom-input label="Email" type="email" placeholder="Escribe tu email"></custom-input>

        <!-- 3. Input de contraseña -->
        <custom-input label="Contraseña" type="password" placeholder="Escribe tu contraseña"></custom-input>

        <!-- 4. Input de número -->
        <custom-input label="Número" type="number" placeholder="Escribe un número"></custom-input>

        <!-- 5. Input de fecha -->
        <ion-item>
          <ion-label>Fecha de Nacimiento</ion-label>
          <ion-datetime display-format="MMM DD, YYYY"></ion-datetime>
        </ion-item>

        <!-- 6. Input de selección -->
        <ion-item>
          <ion-label>Género</ion-label>
          <ion-select placeholder="Selecciona uno">
            <ion-select-option value="masculino">Masculino</ion-select-option>
            <ion-select-option value="femenino">Femenino</ion-select-option>
          </ion-select>
        </ion-item>

        <!-- 7. Input de checkbox -->
        <ion-item>
          <ion-label>Recibir noticias</ion-label>
          <ion-checkbox></ion-checkbox>
        </ion-item>

        <!-- 8. Input de radio -->
        <ion-radio-group>
          <ion-list-header>
            <ion-label>Género</ion-label>
          </ion-list-header>
          <ion-item>
            <ion-label>Masculino</ion-label>
            <ion-radio slot="start" value="masculino"></ion-radio>
          </ion-item>
          <ion-item>
            <ion-label>Femenino</ion-label>
            <ion-radio slot="start" value="femenino"></ion-radio>
          </ion-item>
        </ion-radio-group>

        <!-- 9. Input de slider (range) -->
        <ion-item>
          <ion-label>Rango de edad</ion-label>
          <ion-range min="0" max="100" pin="true"></ion-range>
        </ion-item>

        <!-- 10. Input de toggle -->
        <ion-item>
          <ion-label>Activar notificaciones</ion-label>
          <ion-toggle></ion-toggle>
        </ion-item>
        
        <ion-button expand="block">Enviar</ion-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonItem, IonDatetime, IonSelect, IonSelectOption, IonCheckbox, IonRange, IonRadioGroup, IonRadio, IonToggle, IonButton } from '@ionic/vue';
import CustomInput from '../components/CustomInput.vue';
</script>

<style scoped>
#form-container {
  text-align: left;
  margin: 20px;
}

#form-container strong {
  font-size: 22px;
  margin-bottom: 15px;
  display: block;
}
</style>
```

---
