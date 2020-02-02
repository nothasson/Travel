<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img
        class="banner-img"
        src="//img1.qunarzz.com/sight/p0/1501/18/181cff1e8af11041.water.jpg_600x330_40b06d15.jpg"
      />
      <div class="banner-info">
        <div class="banner-title">维多利亚海港</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63a;</span>
          {{this.imgs.length}}
        </div>
      </div>
    </div>
    <common-gallery :imgs="imgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from "common/gallery/Gallery";
export default {
  name: "DetailBanner",
  components: {
    CommonGallery
  },
  methods: {
    handleBannerClick() {
      this.showGallery = true;
    },
    handleGalleryClose() {
      this.showGallery = false;
    }
  },
  data() {
    return {
      imgs: [
        "http://img1.qunarzz.com/sight/p0/1501/de/deb4f9328baaba7f.water.jpg_r_800x800_af4f8bec.jpg",
        "http://img1.qunarzz.com/sight/p0/1501/a9/a9d9fc7f97ef61b2.water.jpg_r_800x800_0e79421b.jpg"
      ],
      showGallery: false
    };
  }
};
</script>

<style lang="stylus" scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 0.6rem;
    display: flex;
    color: #fff;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));

    .banner-title {
      flex: 1;
      font-size: 0.32rem;
      text-align: left;
      padding: 0 0.2rem;
    }

    .banner-number {
      margin-top: 0.14rem;
      font-size: 0.24rem;
      padding: 0 0.4rem;
      line-height: 0.32rem;
      height: 0.32rem;
      border-radius: 0.2rem;
      background: rgba(0, 0, 0, 0.8);

      .banner-icon {
        font-size: 0.24rem;
      }
    }
  }
}
</style>