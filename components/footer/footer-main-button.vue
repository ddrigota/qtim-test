<template>
  <button
    class="footer__main-button"
    tabindex="-1">
    <span class="footer__main-button-text">Go</span>
  </button>
</template>

<script></script>

<style lang="scss" scoped>
@keyframes gradient {
  0% {
    background: radial-gradient(
      circle at center,
      $color-grey-1,
      $color-purple-dark 0%,
      $color-purple-dark 100%
    );
  }
  25% {
    background: radial-gradient(
      circle at center,
      $color-grey-1,
      $color-purple-dark 25%,
      $color-purple-dark 100%
    );
  }
  50% {
    background: radial-gradient(
      circle at center,
      $color-grey-1,
      $color-purple-dark 50%,
      $color-purple-dark 100%
    );
  }
  75% {
    background: radial-gradient(
      circle at center,
      $color-grey-1,
      $color-purple-dark 75%,
      $color-purple-dark 100%
    );
  }
  100% {
    color: $color-white;
    background: radial-gradient(
      circle at center,
      $color-grey-1,
      $color-purple-dark 100%,
      $color-purple-dark 100%
    );
  }
}

.footer__main-button {
  position: absolute;
  bottom: -179px;
  right: calc(50% - 189px);
  width: 358px;
  height: 358px;
  background-color: $color-grey-1;
  border: none;
  border-radius: 50%;
  font-size: 32px;
  font-weight: 400;
  line-height: 100%;
  color: $color-white;
  transition: transform 0.3s;
  &-text {
    position: relative;
    bottom: 42px;
    left: 0px;
  }
  &:hover {
    transform: scale(1.1);
  }
  &:active {
    animation: gradient 0.2s;
  }
}
</style>
