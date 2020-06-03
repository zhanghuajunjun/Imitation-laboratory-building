<template>
 <div class="box3">
  <div class=" flex-j-sb flex-a-c marg-tbsss">
    <div class=" flex-a-c">
      <span class="three-item hover">楼+ 实战课程</span>
      <span class="three-item padd-lr">|</span>
      <span class="three-item1 hover">定期开班，导师助教全程辅导，最快最优成长</span>
    </div>
    <div class="three-item1 hover">更多></div>
  </div>
  <div class=" d-flex box3">
    
    <div v-for="(item,index) in picture_url" :key="index" class="hover1 hover ccc">
      <div v-if="index < 4" class="three-item2">
        <div><img :src="item.picture_url" width="270"></div>
        <div class=" marg-topsw padd-lr">{{item.title}}</div>
        <div class=" marg-tops padd-lr three-item1 ">最近班次：{{item.open_time}}</div>
      </div>
    </div>
  </div>
 </div>
</template>

<script>
 import axios from 'axios'
 export default {
   name: '',
   props: {

   },
   data () {
     return {
       picture_url: []
     }
   },
   components: {

   },
   methods: {
     getData(){
       axios.get(`http://120.78.14.107/api/v2/index/louplus`).then(res => {
         this.picture_url=res.data
       }).catch(err => {})
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
.three-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656
}
.three-item1 {
  font-size: 14px;
  color: #666;
}
.three-item2 {
  width: 270px;
  border-radius: 10px;
  background: white;
  padding-bottom: 20px;
  overflow: hidden;
}
.ccc {
  width: 23%;
  margin-left: 28px;
  &:first-child{
    margin-left: 0;
  }
}
</style>