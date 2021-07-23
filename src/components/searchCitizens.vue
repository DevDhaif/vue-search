<template>
    <div class="hello">
        <div class="search-wrapper mb-10">
            <input type="text" v-model="search" placeholder="Search a name " class="bg-red-300 w-60 h-12 p-4  placeholder-black">
            <label >Search</label>
        </div>
        <div v-for="citizen in filterdCitizens" :key="citizen.index" >
            

            <div class="bg-green-500">
           <h1 class="text-3xl">Name: {{citizen.fullName}}</h1>
            <h1 class="text-3xl">ID:{{citizen.id}}</h1>
            <h1 class="text-3xl">Gender:{{citizen.gender}}</h1>
            <h1 class="text-3xl">NID:{{citizen.nid}}</h1>
            <h1 class="text-3xl">Religion:{{citizen.religion}}</h1>
            <h1 class="text-3xl">Place Of Birth:{{citizen.placeOfBirth}}</h1>
            <h1 class="text-3xl">Date Of Birth:{{citizen.dateOfBirth}}</h1>
            <h1 class="text-3xl">State:{{citizen.state}}</h1>
            <h1 class="text-3xl">Current State:{{citizen.currentState}}</h1>
            </div>
            
        </div>
    </div>
</template>

// <script>

import axios from 'axios'
export default {
    name:"App.vue",
    props:{
        msg:String
    },
    data(){
        return {
            citizens:[],
            search:'',
        }
    },
    mounted()
    {
      
      axios.get('http://localhost:8000/api/citizen')
        .then(response => {
            this.citizens=response.data.data;
            })
    },
    computed:{
        filterdCitizens(){
            return this.citizens.filter(citizen => {
                return citizen.fullName.toLowerCase().includes(this.search.toLowerCase()) 
            })
        }
    },
}
</script>