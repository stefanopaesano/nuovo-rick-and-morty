<script>
import {store} from '../store.js';
import axios from 'axios';

export default {
    data() {
        return {
            store,
            Searchcharacter:'',
            

        };
    },
    methods: {
        sottomissioneform(){
        const callonecharacter = this.Searchcharacter

        if (callonecharacter.length >0) {
            this.getDataFomApi()
        }
        else{

        }
        },
        getDataFomApi(){
        //   let querystrig = '';

        //   if (callonecharacter.length > 0) {
        //     querystrig = '?name=' + callonecharacter;
        //   }

            axios .get(this.store.baseUrl.quesrystrig).then((response) =>{
        // console.log(response)
        this.store.Characters = response.data.results
        console.log(this.store.Characters)
        })
        console.log(this.store.Characters)

        }
    
            
    }
}
</script>

<template>
    <header>
        <div class="header">
            <div class="row">
                <div class="col-3">
                    <h1>rick and morty api</h1>
                        <form @submit.prevent="sottomissioneform">
                            <nav class="navbar bg-body-tertiary">
                                <div class="container-fluid">
                                    <input v-model="Searchcharacter" class="form-control me-2" type="search" placeholder="Search-character" aria-label="Search-character" style="width: 50%;">
                                    <button class="btn btn-outline-success" type="submit">Search</button>
                                </div>
                            </nav>
                        </form>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
      h1{
        text-align: center;
      }
</style>
