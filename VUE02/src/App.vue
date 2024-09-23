<script>
  export default {
    data() { // Funzione data()
      return  { // ritorna un oggetto
        nome : 'Marco',
        stato: 'pending',
        esamiMancanti: ['Ing. SW Avanz.', 
          'Data Mining', 'Progr. Conc.',
          'Ricerca Operativa'
        ],
        sitoGoogle: "https://google.com",
      };
    },
    methods: { // Oggetto di metodi
      cambiaStato() {
        if(this.stato === 'active') {
          this.status = 'pending';
        }
        else if( this.stato === 'pending') {
          this.stato = 'inactive';
        }
        else {
          this.stato = 'active';
        }
      }
    }  
  }
</script>

<template>
  <h2 v-if="stato === 'active'">Utente e' attivo </h2>
  <h2 v-else-if="stato === 'pending'">Utente e' in pending </h2>
  <h2 v-else>Utente e' inattivo </h2>
  <h3>Esami Mancanti:</h3>
  <ul>
    <li v-for="e in esamiMancanti" :key="esame"> {{ e }}</li>
  </ul>
 
  <a :href="sitoGoogle">Clicca per andare su Google</a>
  <br>
  <button v-on:click="cambiaStato">Cambia stato</button>
</template>