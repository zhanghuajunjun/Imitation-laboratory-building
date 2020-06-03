<template>
  <div class="box3">
    <div class="flex-j-sb flex-a-c marg-tbsss">
      <div class="flex-a-c">
        <span class="ten-item hover">学习路径</span>
        <span class="ten-item padd-lr">|</span>
        <span class="ten-item1 hover">精准而系统的学习路径，从0到大牛</span>
      </div>
      <div class="ten-item1 hover">更多></div>
    </div>
    <div class="d-flex">
      <div v-for="(item,index) in arr" :key="index">
        <div class="ten-item2">
          <div class="ten-item3 hover pos-re hover1">
            <img :src="item.image" alt />
            <div class="ten-item4">{{item.name}}</div>
            <div class="ten-item5">{{item.courses_count}}课程</div>
            <div v-if="index===0" class="pos-ab">
              <img
                src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAVCAYAAAA98QxkAAAAAXNSR0IArs4c6QAAAp9JREFUSA3NlrtLHFEUxn8zGhGNCoqKj2ItfBWKgo1gZy0JurilGEiVP0ASQmQD2dhpilQpLCKiYpNCGxtBsLAQUXQVLAK+wUKMgs/dnDN3d91VY2QdYQ7M3nvPnPvNt98958xYiEWj0aCOXjfLsvozhexrIfqJyUlv8+3qUmHJFJa/ODv7zeamj+Vlb5P2+7FF5ijZ2R8IBP54m61hZ8dIjlNWdkJdnec5O4RF5Yio/FFUPvE647jCyvMnVVXncnmasxadY6LypdPeAoEQAwMv4/57x6YmuLiAtbWb2+3tsLoK+/vGV1EBbW1QVAS7uzAzA6enUF4OGnvbRkfh+vq29846WWG9+YP6+msqK+8EpjhqasDnS3HR0gKFhcbX3Ax9fXBwAPPzJjYUgvx8OJGs0z+2tQWtrWau60gkFe8fqxTCovIZGRlf6e4WKdI0y4LeXhgZgdlZWFqCoSFYXwfppRwfw+IiTgs9PzdzXUuPfYylEHY22PZ3GhosSksf3q9H29h4c+XlmfjiYtC5Ek02JVVbm+xJa57I4cTuSOQdKytR5zgTznsmmjbJx1hQYIKU7NGRyfHkbYeHkJWV7ElrnkJYii6by8v3TEzk/hdtYQGmp2/CNGfVtOhKSkCLbmfH+PRXC1WL74l2OyXeEg5nsL2dPqx2grk56OgAOwavLyTtGFNT6ePGdiYUFnVfSKvqZ3z84Zb2mEcOD0NPDwwOwtUV8lIyRRgOP2b3gzFS0saE8Bs2Nr4RDD6dcBxUO0ZOjum/cV+6Y2cn+P2fnTMTsrZ8sX1hbMw9skpMW5WmiIsWz+EAe3u5orCL0M8DZYu6lqgbktyNNdLneZBbqFp0r6QofFRX41xuIbuNo29JMafoROV+t/GfA08+HYJ/ARwRyXMvBnEHAAAAAElFTkSuQmCC"
                alt
              />
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
        .get(`http://120.78.14.107/api/v2/index/paths`)
        .then(res => {
          this.arr = res.data;
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
.ten-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.ten-item1 {
  font-size: 14px;
  color: #666;
}
.d-flex {
  margin-left: -15px;
  margin-right: -15px;
}
.ten-item2 {
  padding: 0 15px;
}
.ten-item3 {
  background: white;
  height: 270px;
}
.ten-item3:hover {
  transform: translate(0, -10px);
  transition: all .5s;
}
.ten-item4 {
  padding: 30px 0 15px;
  color: #666;
  font-size: 18px;
  text-align: center;
}
.ten-item5 {
  padding: 0 0 30px;
  color: #a4a4a4;
  font-size: 14px;
  text-align: center;
}
.pos-ab {
  top: 10px;
  right: -5px;
}
</style>