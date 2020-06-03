<template>
  <div class="box3">
    <div class="flex-j-sb flex-a-c marg-tbsss">
      <div class="flex-a-c">
        <span class="four-item hover">{{arr.classify_name}}</span>
        <span class="four-item padd-lr">|</span>
        <span class="four-item1 hover">{{arr.description}}</span>
      </div>
      <div class="four-item1 hover">更多></div>
    </div>
    <div class="d-flex marg flex-j-sb">
      <img
        class="hover1 hover marg-bo"
        :src="arr.recommend_course.picture_url"
        alt
        v-if="arr.recommend_course"
      />
      <div v-for="(item,index) in arr.courses" :key="index">
        <div class="four-item2 pos-re hover1 hover">
          <img :src="item.picture_url" alt height="150" width="264" />
          <!-- <h4 class="four-item3">{{item.name}}</h4> -->
          <div class="four-item4">
            <h4 class="four-item7">{{item.name}}</h4>
            <div class="four-item5">{{item.description}}</div>
          </div>
          <div class="abc"></div>
          <div class="four-item6">
            <div>
              <i class="iconfont icon-renqun"></i>
              <span class="four-item8">{{item.students_count}}</span>
            </div>
            <span class="four-item9" v-if="index>1&&index<5">训练营</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "",
  props: {},
  data() {
    return {
      arr: []
    };
  },
  components: {},
  methods: {
    getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/classfication-courses`)
        .then(res => {
          this.arr = res.data[0];
        })
        .catch(err => {});
    }
  },
  mounted() {
    this.getData()
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.four-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.four-item1 {
  font-size: 14px;
  color: #666;
}
.four-item2 {
  background: white;
  width: 264px;
  height: 250px;
}
.four-item3 {
  padding: 20px 10px 0;
  color: #666;
}
.four-item4 {
  padding: 0 10px;
  position: absolute;
  background: white;
  height: 41px;
  overflow: hidden;
  text-overflow: ellipsis;
}
.four-item2:hover .four-item4 {
  height: 113px;
  transition: all 5s;
}
.four-item5 {
  padding-top: 20px;
  font-size: 13px;
  color: #666;
}
.four-item6 {
  font-size: 12px;
  color: #9b9da2;
  padding: 0 10px;
  height: 53px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.four-item7 {
  padding: 20px 0 0;
  color: #666;
}
.four-item8 {
  padding-left: 10px;
}
.marg {
  display: flex;
  flex-wrap: wrap;
}
.four-item9 {
  border-radius: 20px;
  padding: 3px 10px;
  font-size: 12px;
  background: #f66;
  color: #fff;
}
.abc {
  height: 41px;
}
</style>