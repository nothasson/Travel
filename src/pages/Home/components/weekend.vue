<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.content}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  data() {
    return {
      weekendList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/7d/df6ff468331c43.jpg_r_640x214_1f3783d0.jpg",
          title: "上海必游top10",
          content: "中西合璧，现代和传统各有各的精彩"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1511/1d/fe098e8cfec117.jpg_r_640x214_a9be292a.jpg",
          title: "上海城市观光",
          content: "来这里寻找你所认识的上海"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/7b/2a6b0ce087f0e5.jpg_r_640x214_5c76b115.jpg",
          title: "情迷博物馆",
          content: "穿梭时光岁月寻找答案"
        },
        {
          id: 4,
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/b7/2f4621a3a4e12c.jpg_r_640x214_d55c10ba.jpg",
          title: "学生最爱TOP10",
          content: "学习之余最爱玩耍，爱玩的你不可错过"
        }
      ]
    };
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
  margin-top: 0.2rem;
  font-size: 0.3rem;
  text-align: left;
}

.item {
  text-align: left;

  .item-img-wrapper {
    height: 0;
    overflow: hidden;
    padding-bottom: 33.9%;

    .item-img {
      width: 100%;
    }
  }

  .item-info {
    padding: 0.1rem;

    .item-title {
      line-height: 0.52rem;
      font-size: 0.32rem;
      ellipsis();
    }

    .item-desc {
      line-height: 0.4rem;
      color: #ccc;
      ellipsis();
    }
  }
}
</style>