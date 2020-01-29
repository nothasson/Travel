<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img
          class="item-img"
          :src="item.imgUrl"
        />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.content}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg",
          title: "上海迪士尼乐园",
          content: "上海市浦东新区川沙新镇上海迪士尼度假区内"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1502/ba/ba5f873a22327e0f.water.jpg_200x200_9bf5cc14.jpg",
          title: "上海影视乐园",
          content: "上海市松江区车墩镇北松公路4915号"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/tuan/team2/1507/2c/83e0e0e7ae082a.jpg_110x110_24c155d5.jpg",
          title: "东方明珠",
          content: "上海市浦东新区世纪大道1号"
        },
        {
          id: 2,
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1603/17/170481fb9caf500790.water.jpg_200x200_a32b9a92.jpg",
          title: "上海野生动物园",
          content: "上海浦东南汇区南六公路178号"
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
  display: flex;
  height: 1.9rem;
  overflow: hidden;
  text-align: left;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;

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

    .item-button {
      background: #ff9300;
      padding: 0 0.2rem;
      border-radius: 0.06rem;
      margin-top: 0.16rem;
      color: white;
      line-height: 0.44rem;
    }
  }
}
</style>