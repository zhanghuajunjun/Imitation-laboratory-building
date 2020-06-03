<template>
  <div class="box3">
    <div class="flex-j-sb flex-a-c marg-tbsss">
      <div class="flex-a-c">
        <span class="six-item hover">{{arr.classify_name}}</span>
        <span class="six-item padd-lr">|</span>
        <span class="six-item1 hover">{{arr.description}}</span>
      </div>
      <div class="six-item1 hover">更多></div>
    </div>
    <div class="d-flex">
      <div v-for="(item,index) in arr.courses" :key="index">
        <div class="six-item2">
          <div class="six-item3 hover hover1 pos-re">
            <img :src="item.picture_url" alt height="150" width="260.5"/>
            <h4 class="six-item4">{{item.name}}</h4>
            <div class="six-item5">
              <h4 class="six-item8">{{item.name}}</h4>
              <div class="six-item6">{{item.description}}</div>
            </div>
            <div class="six-item7">
              <i class="iconfont icon-renqun"></i>
              <span class="six-item9">{{item.students_count}}</span>
            </div>
            <div v-if="index===0" class="six-item10">新人必学
              <div class="six-item11"></div>
            </div>
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
          this.arr = res.data[2];
        })
        .catch(err => {});
    }
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.six-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.six-item1 {
  font-size: 14px;
  color: #666;
}
.d-flex {
  margin-left: -6px;
}
.six-item2 {
  padding: 0 15px;
  height: 250px;
}
.six-item3 {
  background: white;
  height: 250px;
}
.six-item4 {
  padding: 20px 10px 0;
  color: #666;
}
.six-item5 {
  padding: 0 10px;
  display: none;
  position: absolute;
  background: white;
  left: 0;
  bottom: 53px;
  height: 113px;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  word-wrap: break-word;
  transition: all 1s;
}
.six-item3:hover .six-item5 {
  display: block;
  
  transition: all 1s;
}
.six-item6 {
  padding-top: 20px;
  font-size: 13px;
  color: #666;
}
.six-item7 {
  font-size: 12px;
  color: #9b9da2;
  padding: 0 10px;
  height: 53px;
  display: flex;
  align-items: center;
}
.six-item8 {
  padding: 20px 0 0;
  color: #666;
}
.six-item9 {
  padding-left: 10px;
}
.six-item10 {
  position: absolute;
  top: 0;
  left: -8px;
  padding: 1px 8px;
  color: #fff;
  background: #f66;
  font-size: 12px;
}
.six-item11 {
  content: "";
  position: absolute;
  left: 3px;
  top: 13px;
  z-index: 1;
  border: 5px solid transparent;
  border-bottom-color: #de524d;
  -webkit-transform: rotate(45deg);
  transform: rotate(45deg);
}
</style>