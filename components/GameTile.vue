<template>
  <div
    :class="{'GameTile': true, 'GameTile_isEmpty': isEmpty}"
  >
    {{ number }}
  </div>
</template>

<script>
export default {
  name: 'GameTile',

  props: {
    number: {
      required: true,
      type: Number,
    },
    isEmpty: Boolean,
  },

}
</script>

<style lang="scss">
  @import '~assets/styles/variables';

  $bgColor: $gameTileBg;

  .GameTile {
    display: flex;
    align-items: center;
    justify-content: center;

    font-family: $fontPrimary;
    font-size: 2rem;
    color: $textColorPrimary;
    border-radius: 5%;
    border: 1px solid lighten($bgColor, 5%);
    background: $bgColor;
    cursor: pointer;

    transition: background .1s ease-in;

    &:hover {
      background: darken($bgColor, 5%);
    }

    &::before {
      content: '';
      float: left;
      display: block;
      padding-top: 100%;
    }

    &_isEmpty {
      opacity: 0;
    }
  }
</style>
