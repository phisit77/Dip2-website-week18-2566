<template>
    <div class="container mt-4">
        <div class="row">
            <div class="col-md-3 mb-5 justify-content-md-start" v-for="item in allelder" :key="item.id">
                <div class="card shadow p-0">
                    <img :src="item.imageUrl" class="card-img-top" alt="elder">
                    <div class="card-body">
                        <h5 class="card-title">{{ item.name }}</h5>
                        <p class="card-text">Location - {{ item.location }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { onMounted,ref } from 'vue';

const allelder = ref([]);

onMounted(() => {
    axios.get(`http://localhost:8080/elder`)
        .then((response) => {
            // console.log(response.data)
            allelder.value = response.data
        })
})

</script>

<style lang="scss" scoped></style>