<script lang="ts" setup>
import { reactive } from 'vue'
import type { Student } from '@/models/students'
const student: Student = reactive({
  nom: '',
  prenom: '',
  email: '',
  gender: '',
  adresse: '',
  codePostal: 0,
  ville: '',
  institut: '',
})
const isFormSubmitted = reactive({
  submitted: false
})
const onSubmit = () => {
  console.log(student.nom)
  console.log(student.prenom)
  console.log(student.email)
  console.log(student.gender)
  console.log(student.adresse)
  console.log(student.codePostal)
  console.log(student.ville)
  console.log(student.institut)
  isFormSubmitted.submitted = true
}

</script>
<template>
  <form @submit.prevent="onSubmit">
    <label for="nom">Nom</label>
    <input type="text" id="nom" name="nom" placeholder="Ton nom..." v-model="student.nom" />
    <label for="prenom">Prénom</label>
    <input
      type="text"
      id="prenom"
      name="prenom"
      placeholder="Ton prénom..."
      v-model="student.prenom"
    />
    <label for="email">E-mail</label>
    <input
      type="email"
      name="email"
      id="email"
      placeholder="adresse mail"
      v-model="student.email"
    />
    <label for="gender">Sexe</label>
    <label for="femme">Femme</label>
    <input type="checkbox" name="femme" id="femme" value="Femme" v-model="student.gender" />
    <label for="homme">Homme</label>
    <input type="checkbox" id="homme" name="homme" value="Homme" v-model="student.gender" />
    <label for="adresse">Adresse</label>
    <input
      type="text"
      id="adresse"
      name="adresse"
      placeholder="Adresse..."
      v-model="student.adresse"
    />
    <label for="codePostal">Code Postal</label>
    <input type="number" name="codePostal" id="codePostal" v-model="student.codePostal" />
    <label for="ville">Ville</label>
    <input type="text" id="ville" name="ville" placeholder="Ville..." v-model="student.ville" />
    <label for="institut">Institut</label>
    <input
      type="text"
      id="institut"
      name="institut"
      placeholder="Institut..."
      v-model="student.institut"
    />
    <button type="submit">Enregistrer</button>
  </form>
  <div v-if="isFormSubmitted.submitted">
    <ul>
        <li>Nom: {{ student.nom }}</li>
        <li>Prénom: {{ student.prenom }}</li>
        <li>E-mail: {{ student.email }}</li>
        <li>Genre: {{ student.gender }}</li>
        <li>Adresse: {{ student.adresse }}</li>
        <li>Code postal: {{ student.codePostal }}</li>
        <li>Ville: {{ student.ville }}</li>
        <li>Institut: {{ student.institut }}</li>
    </ul>
  </div>
</template>
<style></style>
