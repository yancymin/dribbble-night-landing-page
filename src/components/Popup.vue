<template>
  <div class="popup" v-show="isShowPopup">
    <i class="fas fa-times" @click="close()"></i>
    <div class="popup_container">
      <img src="../assets/popup_logo.png" alt />
      <h3>Thanks for downloading Dribbble Night!</h3>
      <a href="https://www.buymeacoffee.com/2BJnfEK" target="_blank" class="coffee">
        <img
          src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/black_img.png"
          alt="Buy Me A Coffee"
          style="height: auto !important;width: auto !important;"
        />
      </a>
      <div class="sharer">
        <span>Share with your designer friends</span>
        <ul class="sharer_wrap">
          <li v-for="(iterm,i) in share" :key="i">
            <button
              class="button"
              :data-sharer="iterm[0]"
              data-title="🌗Dribbble Night | Dark Mode for Dribbble"
              data-hashtags="Dribbble Night"
              data-url="https://dribbbbble.com"
            >
              <i :class="iterm[1]"></i>
            </button>
          </li>
        </ul>
      </div>
    </div>
    <span class="mask"></span>
  </div>
</template>

<script>
import sharer from "sharer.js";

export default {
  name: "popup",
  props: ['isShowPopup'],
  methods: {
    close() {
      this.$emit("showPopup", false);
    }
  },
  data() {
    return {
      showPopup: false,
      share: {
        twitter: ["twitter", "fab fa-twitter"],
        facebook: ["facebook", "fab fa-facebook"],
        weibo: ["weibo", "fab fa-weibo"],
        line: ["line", "fab fa-line"],
        pinterest: ["pinterest", "fab fa-pinterest"],
        tumblr: ["tumblr", "fab fa-tumblr"],
        reddit: ["reddit", "fab fa-reddit-alien"],
        buffer: ["buffer", "fab fa-buffer"]
      }
    };
  }
};
</script>

<style lang="scss" scoped>
.closePopup {
  opacity: 0;
  visibility: hidden;
}
.showPopup {
  opacity: 1;
  visibility: visible;
}
.popup {
  // opacity: 0;
  width: 100vw;
  height: 100vh;
  z-index: 99999;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 8px;
  background-color: #1a1a1a;
  font-family: "Montserrat", sans-serif;

  .mask {
    z-index: -1;
    display: inline-block;
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    background: #1a1a1a;
  }

  i {
    font-size: 18px;
    transition: all 0.3s ease;
    &:hover {
      opacity: 0.65;
    }
  }

  .fa-times {
    position: absolute;
    right: 30px;
    top: 31px;
    cursor: pointer;
  }
  .sidepic {
    height: 100vh;
    border-right: 1px solid #515151;
  }

  .popup_container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    padding: 80px;
    background-color: #1a1a1a;

    .coffee {
      position: fixed;
      top: 20px;
      right: 80px;
      mix-blend-mode: luminosity;
      filter: contrast(0.87);
      border: 1px solid #333;
      border-radius: 6px;
      transform: scale(0.8);
      transform-origin: right;
    }

    > img {
      width: 100px;
      height: 100px;
      margin-bottom: 32px;
    }

    h3 {
      font-size: 40px;
      margin-bottom: 80px;
    }

    .sharer {
      span {
        position: relative;

        &::after {
          position: absolute;
          top: 35px;
          left: 38%;
          content: "";
          display: block;
          width: 60px;
          height: 1px;
          background-color: #515151;
        }
      }
      ul {
        margin-top: 40px;
        li {
          display: inline;
          button {
            cursor: pointer;
            border: none;
            background: none;

            i {
              color: white;
            }
          }
        }
      }
    }
  }
}
</style>