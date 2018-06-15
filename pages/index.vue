<template>
  <section class="container Ptp60">
    <div class="auto_box clearfix">
      <ul class="catalog left">
         <li></li>
      </ul>
      <el-carousel trigger="click" height="338px" class="swipper left">
        <el-carousel-item v-for="item in books" :key="item.id">
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
    let textbooks = await axios.get("http://localhost:3003/textbooks");
    return {
      books: textbooks.data
    };
  }
};
</script>

<style lang='scss'>
.container {
  .catalog {
    width: 600px;
  }
  .swipper {
    width: 600px;
  }
}
</style>
