<template>
  <button :class="buttonClass" />
</template>

<script>
const LEFT_SIDE = 'left';
const RIGHT_SIDE = 'right';

const SIDES = [LEFT_SIDE, RIGHT_SIDE];

export default {
  props: {
    side: {
      type: String,
      required: true,
      validator: val => SIDES.includes(val),
    },
  },
  computed: {
    buttonClass() {
      return {
        'atm-button': true,
        'atm-button-left': this.side === LEFT_SIDE,
        'atm-button-right': this.side === RIGHT_SIDE,
      };
    },
  },
};
</script>

<style lang="scss">
$atm-button-color: #ddd;
$atm-button-active-color: #ccc;

.atm-button {
  content: '';
  background: $atm-button-color;
  display: inline-block;
  height: 70px;
  width: 100px;
  border: $atm-button-color;
  position: relative;
  cursor: pointer;

  &:before {
    content: '';
    height: 0;
    position: absolute;
    top: 0;
    width: 0;
    border-bottom: 35px solid transparent;
    border-top: 35px solid transparent;
  }

  &:focus {
    outline: 0;
  }

  &:active {
    background: $atm-button-active-color;
  }

  &.atm-button-left {
    margin-left: 0px;
    margin-right: 20px;
    border-radius: 10px 0 0 10px;

    &:before {
      border-left: 20px solid $atm-button-color;
      right: -20px;
    }

    &:active:before {
      border-left-color: $atm-button-active-color;
    }
  }

  &.atm-button-right {
    margin-left: 20px;
    margin-right: 0px;
    border-radius: 0 10px 10px 0;

    &:before {
      border-right: 20px solid $atm-button-color;
      left: -20px;
    }

    &:active:before {
      border-right-color: $atm-button-active-color;
    }
  }
}
</style>
