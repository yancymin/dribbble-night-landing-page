<template>
  <div class="popup">
    <i class="fas fa-times"></i>
    <img src="../assets/popup_side.png" alt class="sidepic" />
    <div class="popup_container">
      <img src="../assets/popup_logo.png" alt />
      <h3>Thanks for downloading Dribbble Night!</h3>
      <a href="https://www.buymeacoffee.com/2BJnfEK" target="_blank">
        <img
          src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/black_img.png"
          alt="Buy Me A Coffee"
          style="height: auto !important;width: auto !important;"
        />
      </a>
      <div class="sharer">
        <span>Sharing for your designer friends.</span>
        <ul class="sharer_wrap">
          <li>
            <button
              class="button"
              :data-sharer="iterm[0]"
              data-title="🌗Dribbble Night | Dark Mode for Dribbble"
              data-hashtags="Dribbble Night"
              data-url="https://dribbbbble.com"
              v-for="(iterm,i) in share"
              :key="i"
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
  data() {
    return {
      share: {
        twitter: ['twitter','fab fa-twitter'],
        facebook: ['facebook','fab fa-facebook'],
      }
    };
  }
};
</script>

<style lang="scss" scoped>
.popup {
  min-width: 240px;
  z-index: 99999;
  position: fixed;
  top: 25vh;
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
    background: rgba(217, 89, 136, 0.7);
  }

  i {
    font-size: 18px;
    transition: all 0.3s ease;
    &:hover {
      opacity: 0.7;
    }
  }

  .fa-times {
    position: absolute;
    right: -24px;
    top: 0;
    cursor: pointer;
  }
  .sidepic {
    width: 240px;
    border-top-left-radius: 8px;
    border-bottom-left-radius: 8px;
  }

  .popup_container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    padding: 80px;
    background-color: #1a1a1a;

    > img {
      width: 100px;
      height: 100px;
      margin-bottom: 32px;
    }

    h3 {
      font-size: 24px;
    }
  }
}
</style>