<script setup>
import linkedin from '/src/assets/linkedin_icon.svg';
import instagram from '/src/assets/instagram_icon.svg';
import github from '/src/assets/github_icon.svg';
import face from '/src/assets/facebook_icon.svg';
// Cambia 'mi-foto.jpg' por el nombre real de tu archivo
import profilePhoto from '/src/assets/mi-foto.jpg'; 


const title = 'Fabio Arreceygor';
const descripcion = 'Estudiante de Tecnicatura Universitaria en Programación - UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = '¡Bienvenido a mi portafolio! Me encuentro en formación en diversos lenguajes de programación, descubriendo los distintos usos de los mismos a través de proyectos y actividades.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin, url: 'https://www.linkedin.com/in/fabio-adriel-arreceygor-544b00258/' },
  { id: 2, name: 'Instagram', src: instagram, url: 'https://www.instagram.com/f.arreceygor/' },
  { id: 3, name: 'github', src: github, url: 'https://github.com/farreceygor' },
  { id: 4, name: 'facebook', src: face, url: 'https://www.facebook.com/FabioArreceygor' },
];
const telefono = '+54 9 2604-598324';
</script>

<template>
  <section class="datos-personales">
    <div class="card">
          <div class="header-presentacion">
        <img :src="profilePhoto" alt="Foto de perfil de Fabio Arreceygor" class="profile-photo">
        <h1>{{ title }}</h1>
      </div>

      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
          <a :href="red.url"><img class="icon-redsocial" :src="red.src" width="35rem" :alt="red.name"></a>
        </li>
      </ul>
      <h3>☎ Mi Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
  </section>
</template>

<style scoped>
/* Contenedor para centrar la foto y el nombre */
.header-presentacion {
  display: flex; 
  align-items: center; 
  justify-content: center; 
  margin-bottom: 0.5rem; 
}

/* Estilos de la foto de perfil */
.profile-photo {
  width: 90px;
  height: 90px; 
  border-radius: 50%;
  object-fit: cover;
  margin-right: 15px; 
  border: 3px solid rgb(209, 183, 148); /* Borde claro para contraste */
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.3);
}

h1 {
  font-size: 2.5rem;
  margin: 0; /* Remueve margen para mejor control con flexbox */
  color: var(--vt-c-white); /* El color blanco contrasta bien con --vt-c-indigo */
}

h2 {
    font-size: 1.5rem;
    color: rgb(209, 183, 148); /* Mantiene el color de la descripción */
    margin-top: 0.5rem;
    margin-bottom: 1rem;
}

p {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--vt-c-white); /* El color blanco contrasta bien con --vt-c-indigo */
}

.card {
  background-color: var(--vt-c-indigo); /* Usa la variable global de color de acento */
  border-radius: 10px;
  padding: 15px;
  margin: 20px auto; /* Centra la tarjeta y da espacio */
  max-width: 600px; /* Limita el ancho de la tarjeta */
  text-align: center;
}

.container-lista {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}

.icon-redsocial {
  align-items: center;
  background-color: var(--vt-c-white); /* Usa la variable de blanco para el fondo del icono */
  border-radius: 50%;
  padding: 2px;
  margin: 5px;
  box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}

.icon-redsocial:hover {
  background-color: var(--vt-c-black-mute); /* Color más oscuro al pasar el ratón */
  box-shadow: 0 0 5px rgba(251, 249, 249, 0.934);
}

h3 {
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--vt-c-white); /* El color blanco contrasta bien con --vt-c-indigo */
}

h4 {
    color: var(--vt-c-white); /* Asegura que la residencia se vea bien */
}
</style>