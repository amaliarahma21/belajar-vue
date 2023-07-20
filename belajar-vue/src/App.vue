<script setup>
let msg = "Halo Dunia";
let headName = "<h1>Nama Saya Amalia</h1>";
let number = 7;
let ok = "YES";
let seen = 1;

</script>

<template>
  <div>
    <span>{{ msg }}</span> <br>
    <span style="color: blue">Ini Warna Merah</span><br>
    <span v-html="headName"></span><br>

    <!-- atribut -->
    <div v-bind:id="dynamicId"></div>
    <button v-bind:disabled="isButtonDisabled">Tombol</button>

  <!-- ekspresif js -->
    {{ number + 1 }} <br>
    {{ ok ? 'YES' : 'NO' }} <br> 
    {{ msg.split('').reverse().join('')
    }}
    <div v-bind:id="'list-' + id"></div>

    <!-- direktri -->
     <p v-if="seen">Sekarang Anda bisa melihatku</p> 

    <!-- argumen -->
    <br>
    <a v-bind:href="url"> Amalia</a><br>
    <a v-on:click="doSomething">Rahma</a>
    
    <!-- argumen dinamis -->
    <br>
    <a v-bind:[namaAtribut]="url">Aku</a><br>
    <a v-on:[namaEvent]="doSomething">Kamu</a>

    <!-- modifier -->
    <form v-on:submit.prevent="onSubmit">Siapa</form>

  <!-- Singkatan v-bind -->
    <!-- full syntax -->
    <a v-bind:href="url"> Gakenal </a><br>

    <!-- singkatan -->
    <a :href="url"> Apa </a><br>

    <!-- singkatan dengan argumen dinamis (2.6.0+) -->
    <a :[key]="url"> Iya </a><br>

  <!-- Singkatan v-on -->
    <!-- full syntax -->
    <a v-on:click="doSomething"> Aman </a><br>

    <!-- singkatan -->
    <a @click="doSomething"> Amin </a><br>

    <!-- singkatan argumen dinamis (2.6.0+) -->
    <a @[event]="doSomething"> Amun </a><br>
  </div>
</template>