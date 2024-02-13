<script setup>
import { toast } from 'vue3-toastify';
import 'vue3-toastify/dist/index.css';

toast.info("ยินดีต้อนรับแผนกเทคโนโลยีสารสนเทศ", {
  autoClose: 1500,
  position:toast.POSITION.TOP_CENTER
})

const notify = () => {
  toast.success("ยินดีต้อนรับแผนกเทคโนโลยีสารสนเทศ", {
    autoClose: 1500,
    position: toast.POSITION.TOP_CENTER
  })
  return notify
}

</script>

<template>
  <div class="container my-5">
    <div class="card shadow" style="width: 20rem;">
      <div class="card-header p-0">
        <img src="https://scontent.fbkk21-1.fna.fbcdn.net/v/t1.6435-9/123468338_198739328479048_8019884579575129978_n.jpg?_nc_cat=108&ccb=1-7&_nc_sid=7f8c78&_nc_ohc=uPWMyy8y0WQAX8AKJ7G&_nc_ht=scontent.fbkk21-1.fna&oh=00_AfCNdIsZxh1eTyPtGzwI7hBt5ICOCaEghSWH5inCsz1IhQ&oe=65F2A450" class="card-img-top"
          alt="img">
      </div>
      <div class="card-body">
        <h5 class="card-title">Monster Hunter World</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary" @click="notify">Read...</a>
      </div>
    </div>
  </div>
</template>
