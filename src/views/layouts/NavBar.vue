<script setup>
import router from '@/router';
import { RouterLink } from 'vue-router'

const logOut = async () => {
    localStorage.clear()
    await router.push({ name: 'signin' })
}

</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-dark shadow" style="background: #47088e;">
        <div class="container">
            <RouterLink :to="{ name: 'home' }" class="navbar-brand">Monster Hunter</RouterLink>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <RouterLink :to="{ name: 'home' }" class="nav-link active" aria-current="page"><i
                                class="bi bi-house-fill me-1"></i>หน้าแรก</RouterLink>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{ name: 'signin' }" class="nav-link" href="#"><i
                                class="bi bi-bank me-1"></i>เข้าสู่ระบบ</router-link>
                    </li>

                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                            aria-expanded="false">
                            <i class="bi bi-bank2 me-1"></i>Dragons
                        </a>

                        <ul class="dropdown-menu">
                            <li>
                                <RouterLink :to="{ name: 'wonders' }" class="dropdown-item">Elder Dragon
                                </RouterLink>
                            </li>
                            <li>
                                <RouterLink :to="{ name: 'add-wonder' }" class="dropdown-item">เพิ่มเนื้อหา
                                </RouterLink>
                            </li>
                            <li><a class="dropdown-item" href="#">แก้ไขเนื้อหา</a></li>
                            <li><a class="dropdown-item" href="#">ลบเนื้อหา</a></li>
                            <li>
                                <hr class="dropdown-divider">
                            </li>
                            <li><a class="dropdown-item" href="https://www.wonderspodcast.com/wonders">เว็บไซต์ Monster Hunter World</a></li>
                        </ul>
                    </li>

                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                            aria-expanded="false">
                            <i class="bi bi-bank2 me-1"></i>เกี่ยวกับเรา
                        </a>
                        <ul class="dropdown-menu">
                            
                            <li>
                                <RouterLink :to="{ name: 'about' }" class="dropdown-item">วิสัยทัศน์</RouterLink>
                            </li>
                           
                            <li>
                                <hr class="dropdown-divider">
                            </li>
                            <li><a class="dropdown-item" href="#">ติดต่อเรา</a></li>
                        </ul>
                    </li>

                    
                    <li class="nav-item">
                        <a class="nav-link" href="#">เว็บอื่นๆ</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#" @click="logOut"><i
                                class="bi bi-box-arrow-right me-1"></i>ออกจากระบบ</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sarabun&display=swap');

.navbar {
    font-family: 'Sarabun', sans-serif;
}
</style>
