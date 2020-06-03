<template>
 <div class="box3">
   <div class="flex-j-sb flex-a-c marg-tbsss">
      <div class="flex-a-c">
        <span class="five-item hover">{{arr.classify_name}}</span>
        <span class="five-item padd-lr">|</span>
        <span class="five-item1 hover">{{arr.description}}</span>
      </div>
      <div class="five-item1 hover">更多></div>
    </div>
 </div>
</template>

<script>
 import axios from "axios";
 export default {
   name: '',
   props: {

   },
   data () {
     return {
       arr: []
     }
   },
   components: {

   },
   methods: {
     getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/classfication-courses`)
        .then(res => {
          this.arr = res.data[1];
        })
        .catch(err => {});
    }
   },
   mounted() {
     this.getData()
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
.five-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.five-item1 {
  font-size: 14px;
  color: #666;
}
</style>