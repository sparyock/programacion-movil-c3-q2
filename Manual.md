# Documentación de la Aplicación Gimnasio Tello

## Índice

1. Pantalla de Login - Gimnasio Tello
   - Objetivo
   - Descripción de la Interfaz
   - Estructura del Código
   - Estilos Personalizados
   - Conclusión

2. CRUD de Gestión de Miembros
   - Introducción
   - Objetivo
   - Descripción del Proyecto
   - Componentes y Funcionalidades
   - Estructura del Código
   - Consideraciones de Diseño
   - Conclusión

---

## Pantalla de Login - Gimnasio Tello

### Introducción

Esta sección describe la estructura y funcionalidad de la pantalla de **Login** de la aplicación **Gimnasio Tello**. La pantalla de login permite que los usuarios ingresen sus credenciales para acceder a la plataforma del gimnasio y proporciona opciones adicionales para recuperar la contraseña o registrarse en caso de que aún no tengan una cuenta.

### Objetivo

El objetivo de esta pantalla de login es proporcionar una interfaz amigable y funcional que permita a los usuarios iniciar sesión de manera fácil y rápida. Además, ofrece enlaces y botones adicionales que mejoran la experiencia del usuario al permitir el acceso a información y soporte.

### Descripción de la Interfaz

La pantalla de login está organizada en varios componentes clave:

1. **Logo del Gimnasio**: Una imagen representativa de la marca, ubicada en la parte superior de la pantalla.
2. **Texto de Bienvenida**: Un mensaje de bienvenida personalizado con el nombre del gimnasio.
3. **Campo de Usuario**: Un campo de entrada para que el usuario ingrese su nombre de usuario o correo electrónico.
4. **Campo de Contraseña**: Un campo de entrada con tipo de contraseña para ingresar la clave de acceso.
5. **Checkbox de Recordarme**: Una opción que permite al usuario guardar sus credenciales para futuros inicios de sesión.
6. **Botón de Iniciar Sesión**: Botón principal para enviar el formulario de inicio de sesión.
7. **Enlace para Recuperar Contraseña**: Enlace que permite al usuario redirigirse a una página para restablecer su contraseña.
8. **Botón de Registro**: Botón secundario para que los nuevos usuarios se registren.
9. **Opciones adicionales (Información y Soporte)**: Botones que permiten acceder a información adicional sobre el gimnasio y a opciones de contacto para soporte.
10. **Pie de Página**: Una sección final que incluye enlaces a la política de privacidad y los términos de servicio.

### Estructura del Código

#### Template

```html
<template>
  <ion-content class="login-page">
    <!-- Logo del Gimnasio -->
    <ion-img src="/src/assets/logo.jpg" alt="Gym Logo" class="gym-logo"></ion-img>

    <!-- Texto de Bienvenida -->
    <ion-text color="primary">
      <h2>¡Bienvenido a Gimnasio Tello!</h2>
    </ion-text>
    
    <!-- Campo de Usuario -->
    <ion-item>
      <ion-label position="floating">Usuario</ion-label>
      <ion-input type="text" placeholder="Ingrese su usuario o correo"></ion-input>
    </ion-item>
    
    <!-- Campo de Contraseña -->
    <ion-item>
      <ion-label position="floating">Contraseña</ion-label>
      <ion-input type="password" placeholder="Ingrese su contraseña"></ion-input>
    </ion-item>
    
    <!-- Checkbox de Recordarme -->
    <ion-item lines="none">
      <ion-checkbox slot="start"></ion-checkbox>
      <ion-label>Recordarme</ion-label>
    </ion-item>
    
    <!-- Botón de Iniciar Sesión -->
    <ion-button expand="block" color="primary">Iniciar Sesión</ion-button>
    
    <!-- Enlace para Recuperar Contraseña -->
    <ion-text color="medium">
      <small><a href="/forgot-password">¿Olvidaste tu contraseña?</a></small>
    </ion-text>
    
    <!-- Botón de Registro -->
    <ion-button expand="block" color="secondary" fill="outline">Registrarse</ion-button>
    
    <!-- Botones adicionales: Información y Soporte -->
    <ion-text color="medium">
      <p>Más opciones:</p>
    </ion-text>
    <div class="additional-buttons">
      <ion-button expand="block" color="tertiary">Información del Gimnasio</ion-button>
      <ion-button expand="block" color="tertiary">Contacto y Soporte</ion-button>
    </div>
    
    <!-- Pie de Página -->
    <ion-footer class="footer">
      <ion-text color="medium">
        <small>Política de Privacidad | Términos y Condiciones</small>
      </ion-text>
    </ion-footer>
  </ion-content>
</template>

  <!-- Estilos Personalizados-->
.gym-logo {
  width: 150px;
  height: auto;
  margin: 20px auto;
  display: block;
}

.additional-buttons {
  margin-top: 20px;
}
```
### Conclusión
La pantalla de login de Gimnasio Tello fue diseñada para proporcionar una experiencia de usuario amigable y profesional. Los elementos clave como el logo, campos de entrada, botones de acción, y opciones adicionales aseguran que el usuario pueda acceder fácilmente a sus datos y obtener ayuda si lo necesita. El uso de Ionic Vue permite que esta interfaz se adapte bien en dispositivos móviles, mejorando la accesibilidad y usabilidad de la aplicación.


# CRUD de Gestión de Miembros - Gimnasio Tello

## Introducción

Este documento describe la estructura y funcionalidad del sistema **CRUD** (Crear, Leer, Actualizar, Eliminar) para la gestión de miembros del gimnasio **Gimnasio Tello**. Este sistema permite al personal registrar y administrar la información de los miembros, incluyendo el nombre, rol y tipo de membresía.

## Objetivo

Desarrollar una aplicación de gestión para el gimnasio que permita al personal registrar y administrar la información de los miembros, mejorando la organización y accesibilidad a los datos.

## Descripción del Proyecto

La aplicación de **Gestión de Gimnasio** fue creada usando **Vue.js** en el entorno **Ionic Framework**. Las operaciones principales de este CRUD incluyen:

- **Crear**: Añadir nuevos miembros con datos como nombre, rol y membresía.
- **Leer**: Visualizar la lista de miembros registrados.
- **Actualizar**: Editar la información de un miembro.
- **Eliminar**: Eliminar un miembro del sistema.

## Componentes y Funcionalidades

1. **IonPage**: Componente raíz que contiene la página principal.
2. **IonHeader**: Contenedor para el encabezado de la página con el título.
3. **IonContent**: Contenedor principal de la página.
4. **IonList y IonItem**: Para organizar y mostrar el formulario de entrada y la lista de miembros.
5. **IonInput**: Campos de entrada para capturar el nombre y rol del miembro.
6. **IonSelect y IonSelectOption**: Selector de tipo de membresía (Básica, Premium, VIP).
7. **IonButton**: Botones para acciones de CRUD (Añadir, Editar, Eliminar).
8. **IonModal**: Modal para editar información de los miembros.

## Estructura del Código

### Template

```html
<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Gestión de Gimnasio</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <!-- Formulario de nuevo miembro -->
      <ion-list>
        <ion-item>
          <ion-input v-model="newItem.name" placeholder="Nombre"></ion-input>
        </ion-item>
        <ion-item>
          <ion-input v-model="newItem.role" placeholder="Rol (Cliente, Entrenador, etc.)"></ion-input>
        </ion-item>
        <ion-item>
          <ion-select v-model="newItem.membership" placeholder="Membresía">
            <ion-select-option value="Básica">Básica</ion-select-option>
            <ion-select-option value="Premium">Premium</ion-select-option>
            <ion-select-option value="VIP">VIP</ion-select-option>
          </ion-select>
        </ion-item>
        <ion-button expand="full" @click="addItem">Añadir</ion-button>
      </ion-list>

      <!-- Lista de miembros -->
      <ion-list>
        <ion-item v-for="(item, index) in items" :key="index">
          <ion-label>
            <h2>{{ item.name }}</h2>
            <p>{{ item.role }}</p>
            <p>Membresía: {{ item.membership }}</p>
          </ion-label>
          <ion-button fill="clear" color="primary" @click="editItem(index)">Editar</ion-button>
          <ion-button fill="clear" color="danger" @click="deleteItem(index)">Eliminar</ion-button>
        </ion-item>
      </ion-list>

      <!-- Modal para editar miembro -->
      <ion-modal :is-open="isModalOpen" @ionModalDidDismiss="closeModal">
        <ion-header>
          <ion-toolbar>
            <ion-title>Editar</ion-title>
          </ion-toolbar>
        </ion-header>
        <ion-content>
          <ion-list>
            <ion-item>
              <ion-input v-model="editableItem.name" placeholder="Nombre"></ion-input>
            </ion-item>
            <ion-item>
              <ion-input v-model="editableItem.role" placeholder="Rol"></ion-input>
            </ion-item>
            <ion-item>
              <ion-select v-model="editableItem.membership" placeholder="Membresía">
                <ion-select-option value="Básica">Básica</ion-select-option>
                <ion-select-option value="Premium">Premium</ion-select-option>
                <ion-select-option value="VIP">VIP</ion-select-option>
              </ion-select>
            </ion-item>
            <ion-button expand="full" @click="updateItem">Guardar</ion-button>
          </ion-list>
        </ion-content>
      </ion-modal>
    </ion-content>
  </ion-page>
</template>

```
### Script

```html
import { ref } from 'vue';
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonList,
  IonItem,
  IonLabel,
  IonButton,
  IonInput,
  IonModal,
  IonSelect,
  IonSelectOption,
} from '@ionic/vue';

export default {
  components: {
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonList,
    IonItem,
    IonLabel,
    IonButton,
    IonInput,
    IonModal,
    IonSelect,
    IonSelectOption,
  },
  setup() {
    const items = ref([]); // Lista de miembros
    const newItem = ref({ name: '', role: '', membership: '' }); // Nuevo miembro temporal
    const editableItem = ref({}); // Miembro en edición
    const isModalOpen = ref(false); // Estado del modal de edición
    const currentIndex = ref(null); // Índice del miembro en edición

    // Añadir un nuevo miembro
    const addItem = () => {
      if (newItem.value.name && newItem.value.role && newItem.value.membership) {
        items.value.push({ ...newItem.value });
        newItem.value = { name: '', role: '', membership: '' }; // Resetea el formulario
      }
    };

    // Abrir modal para editar un miembro
    const editItem = (index) => {
      currentIndex.value = index;
      editableItem.value = { ...items.value[index] };
      isModalOpen.value = true;
    };

    // Guardar cambios en un miembro
    const updateItem = () => {
      if (currentIndex.value !== null) {
        items.value[currentIndex.value] = { ...editableItem.value };
        closeModal();
      }
    };

    // Eliminar un miembro
    const deleteItem = (index) => {
      items.value.splice(index, 1);
    };

    // Cerrar el modal de edición
    const closeModal = () => {
      isModalOpen.value = false;
    };

    return {
      items,
      newItem,
      editableItem,
      isModalOpen,
      addItem,
      editItem,
      updateItem,
      deleteItem,
      closeModal,
    };
  },
};

</script>

<style scoped>
/* Estilo para los campos de entrada y botón en el formulario */
ion-input {
  margin-bottom: 8px;
}
ion-button {
  margin: 8px 0;
}
</style>


```
### Consideraciones de Diseño

Usabilidad: La interfaz está diseñada para ser intuitiva y simple, permitiendo una gestión rápida de los datos de los miembros.
Accesibilidad: Los componentes de Ionic aseguran una buena experiencia de usuario en dispositivos móviles.
Escalabilidad: Este CRUD permite añadir fácilmente nuevos campos o filtros en el futuro.
### Conclusión
El desarrollo de esta aplicación CRUD para la gestión de miembros permite un control eficaz de los datos en el gimnasio. La implementación en Ionic Vue facilita el desarrollo multiplataforma, proporcionando una experiencia uniforme en dispositivos móviles.

### Referencias
- Vue.js Documentation: https://vuejs.org
- Ionic Framework Documentation: https://ionicframework.com/docs

