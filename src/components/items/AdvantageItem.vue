<template>
  <div class="advantage-item">
    <img :src="advantageItem.icon" :alt="advantageItem.name" />
    <p class="name">{{ advantageItem.name }}</p>
    <span class="description">
      {{ advantageItem.description }}
    </span>
    <div class="border top"></div>
    <div class="border right"></div>
    <div class="border bottom"></div>
    <div class="border left"></div>
  </div>
</template>

<script>
export default {
  props: {
    advantageItem: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.advantage-item {
  position: relative;
  padding: 46px 32px;
  width: calc((100% / 4) - 20px);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
  @media screen and (max-width: 1023px) {
    width: calc(50% - 20px);
    gap: 0.4rem;
  }
  @media screen and (max-width: 767px) {
    gap: 0.3rem;
  }
  @media screen and (max-width: 599px) {
    width: 100%;
  }
  &:hover {
    @media screen and (min-width: 1024px) {
      & .border.top,
      & .border.bottom {
        width: 100%;
      }
      & .border.left,
      & .border.right {
        height: 100%;
      }
    }
    & .name::after {
      width: 100px;
      @media screen and (max-width: 1023px) {
        width: 40px;
      }
    }
  }
  & img {
    width: 36px;
    @media screen and (max-width: 1023px) {
      width: 0.6rem;
    }
  }
  & .name {
    @media screen and (max-width: 1023px) {
      font-size: 0.3rem;
      font-weight: 500;
      margin-bottom: 0.1rem;
    }
    font-size: 16px;
    position: relative;
    &::after {
      transition: 0.8s;
      content: "";
      display: inline-block;
      position: absolute;
      height: 2px;
      width: 40px;
      background-color: #0f7bff;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
    }
  }
  & .description {
    color: #666666;
    text-align: justify;
    @media screen and (max-width: 1023px) {
      font-size: 0.26rem;
      font-weight: 500;
      line-height: 0.4rem;
      font-weight: 500;
    }
  }
  .border {
    position: absolute;
    background-color: #0f7bff;
    transition: 0.3s;
    @media screen and (max-width: 1023px) {
      background-color: #dddddd;
    }
    &.top {
      width: 0;
      height: 1px;
      top: 0;
      left: 0;
      @media screen and (max-width: 1023px) {
        width: 80%;
      }
    }
    &.right {
      width: 1px;
      height: 0;
      right: 0;
      top: 0;
      @media screen and (max-width: 1023px) {
        height: 80%;
      }
    }
    &.bottom {
      height: 1px;
      width: 0;
      right: 0;
      bottom: 0;
      @media screen and (max-width: 1023px) {
        width: 80%;
      }
    }
    &.left {
      width: 1px;
      height: 0;
      left: 0;
      bottom: 0;
      @media screen and (max-width: 1023px) {
        height: 80%;
      }
    }
  }
}
</style>