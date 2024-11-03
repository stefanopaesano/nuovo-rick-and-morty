<script>
import SIngleCharacter from './SIngleCharacter.vue';
import {store} from '../store.js';



export default {
    data() {
        return {
            store,

        };
    },
    methods: {
        changepraize(){
            let prezzoBase = 30;
            let sconto = 0.15;
            let prezzototale = this.prezzoBase * (1 - sconto);
            console.log(this.prezzoBase)
        }

    },
    components:{
          SIngleCharacter
    },
    
  
   
}
</script>

<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col-3" v-for="(Character,i) in store.Characters">
                    <SIngleCharacter :Character="Character"/>
                </div>
            </div>


            
        </div>
        
    </main>
</template>

<style lang="scss" scoped>


.single-character {
    text-align: center; /* Allinea il contenuto al centro */
}

.imge {
    width: 100%; /* Dimensione del cerchio */
    height: 100%; /* Dimensione del cerchio */
    border-radius: 50%; /* Rende il contenitore circolare */
    border: 3px solid red; /* Bordo rosso */
    overflow: hidden; /* Nasconde l'eccesso dell'immagine */
    display: flex; /* Usa flexbox per centrare l'immagine */
    justify-content: center; /* Allinea l'immagine al centro orizzontalmente */
    align-items: center; /* Allinea l'immagine al centro verticalmente */
}

.imge img {
    width: 100%; /* Rende l'immagine larga come il contenitore */
    height: 100%; /* Rende l'immagine alta come il contenitore */
    object-fit: cover; /* Adatta l'immagine all'interno del contenitore */
}

</style>
