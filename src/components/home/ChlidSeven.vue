<template>
  <div class="box3">
    <div class="flex-j-sb flex-a-c marg-tbsss">
      <span class="seven-item hover">{{arr.classify_name}}</span>
      <div class="seven-item1 hover">更多></div>
    </div>
    <div class="d-flex">
      <div class="seven-item2">
        <img
          class="hover hover1"
          :src="arr.recommend_course.picture_url"
          alt
          v-if="arr.recommend_course"
        />
      </div>
      <div class="row">
        <div v-for="(item,index) in arr.courses" :key="index">
          <div class="seven-item2">
            <div class="seven-item3 hover hover1 pos-re">
              <img :src="item.picture_url" alt height="150" width="263" />
              <h4 class="seven-item4">{{item.name}}</h4>
              <div class="seven-item5">
                <h4 class="seven-item8">{{item.name}}</h4>
                <div class="seven-item6">{{item.description}}</div>
              </div>
              <div class="seven-item7">
                <div>
                  <i class="iconfont icon-renqun"></i>
                  <span class="seven-item9">{{item.students_count}}</span>
                </div>
                <span class="seven-item10" v-if="index===0||index===4||index===5">训练营</span>
                <span class="seven-item11" v-if="index===1||index===3">会员</span>
              </div>
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
          this.arr = res.data[3];
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
.seven-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.seven-item1 {
  font-size: 14px;
  color: #666;
}
.d-flex {
  margin-left: -15px;
  margin-right: -15px;
}
.row {
  display: flex;
  flex-wrap: wrap;
  margin-right: -15px;
}
.seven-item2 {
  padding: 0 15px;
}
.seven-item3 {
  background: white;
  height: 250px;
}
.seven-item4 {
  padding: 20px 10px 0;
  color: #666;
}
.seven-item5 {
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
.seven-item3:hover .seven-item5 {
  display: block;
  transition: all 1s;
}
.seven-item6 {
  padding-top: 20px;
  font-size: 13px;
  color: #666;
}
.seven-item7 {
  font-size: 12px;
  color: #9b9da2;
  padding: 0 10px;
  height: 53px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.seven-item8 {
  padding: 20px 0 0;
  color: #666;
}
.seven-item9 {
  padding-left: 10px;
}
.seven-item10 {
  border-radius: 20px;
  padding: 3px 10px;
  font-size: 12px;
  background: #f66;
  color: #fff;
}
.seven-item11 {
  border-radius: 20px;
  padding: 3px 10px;
  font-size: 12px;
  background: #ffc500;
  color: #fff;
}
</style>