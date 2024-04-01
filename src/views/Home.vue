<script>
import dataSource from '@/data.json';

export default {
    data(){
        return{
            destinations: dataSource.destinations
        }
    }
}
</script>

<template>
    <div class="home">
        <h1>Home</h1>
        <div class="destinations">
            <router-link v-for="destination in destinations" :key="destination.id"
                :to="{name: 'destination.show', params: {id: destination.id, slug: destination.slug}}">
                <h2>{{destination.name}}</h2>
                <img :src="`/images/${destination.image}`" :alt="destination.name">
            </router-link>
        </div>
    </div>
</template>