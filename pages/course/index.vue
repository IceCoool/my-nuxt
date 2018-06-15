<template>
  <section class="container Ptp60">
    <div class='auto_box'>
      <el-carousel trigger="click" height="380px">
        <el-carousel-item v-for="item in course" :key="item.id">
          <nuxt-link :to="`/course/${item.id}?type=${item.name}`">
            <img :src="item.cover" alt="">
          </nuxt-link>
        </el-carousel-item>
      </el-carousel>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {};
  },
  async asyncData(context) {
    let res = await axios.get("http://localhost:3003/course");
    return {
      course: res.data,
    };
  }

  //-----------------------------------不同写法

  // asyncData(context){
  //   return axios.get('http://localhost:3003/course')
  //   .then((res) => {
  //     return {
  //       course: res.data
  //     }
  //   })
  // },
  // mounted(){
  //   this.init()
  // },
  // methods: {
  //   init(){
  //     axios.get('http://localhost:3003/course')
  //     .then((res) =>{
  //       this.course = res.data
  //   })
  //   }
  // }
};
</script>

<style>
.container {
}
</style>
