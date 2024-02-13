<template>
    <div class="container mt-4">
        <div class="row">

            <div class="col-md-5 mb-1 mx-auto">
                <div class="card shadow">
                    <div class="card-header p-0">
                        <img src="https://i.ytimg.com/vi/sCCQXtSvBk8/maxresdefault.jpg" class="card-img-top" alt="elder">
                    </div>
                </div>
            </div>

            <div class="col-md-6 mx-auto">
                <div class="card shadow">
                    <div class="card-header " style="background-color: rgb(84, 33, 123)">
                        <span class="text-white fs-5">
                            ลงทะเบียนมังกรโบราณ
                        </span>
                    </div>
                    <div class="card-body text-success">
                        <form @submit.prevent="addWonder">
                            <div class="mb-1">
                                <label for="">ชื่อของมังกร</label>
                                <input type="text" class="form-control" v-model="wonderState.name" />
                            </div>
                            <div class="mb-1">
                                <label for="">ลักษณะ</label>
                                <input type="text" class="form-control" v-model="wonderState.label" />
                            </div>
                            <div class="mb-1">
                                <label for="">ลิงค์ภาพ</label>
                                <input type="text" class="form-control" v-model="wonderState.imageUrl" />
                            </div>

                            <div class="mb-1">

                                <button type="submit" class="btn  text-white shadow" style="background-color: rgb(84, 33, 123)">
                                    ลงทะเบียนมังกรโบราณ
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { reactive } from 'vue';
import { useRouter } from 'vue-router';

const wonderState = reactive({
    name: '',
    location: '',
    imageUrl:''
})

const router = useRouter()

const addWonder = async () => {
    await axios.post(`https://json-server-vue3-d109.onrender.com/wonders`,wonderState)
        .then(() => {
            console.log(wonderState)
            router.push({name:'wonders'})
        })
    alert('ลงทะเบียนสิ่งมหัศจรรย์ของโลก เรียบร้อยแล้ว')
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sarabun&display=swap');

.container {
    font-family: 'Sarabun', sans-serif;

}

.form-label {
    color: green;
}
</style>