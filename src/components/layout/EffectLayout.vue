<template>
  <div id="body">
    <the-header></the-header>
    <section class="container">
      <slot></slot>
    </section>
    <the-footer></the-footer>
  </div>
</template>
<script lang="ts">
import TheHeader from "./effect/TheHeader.vue";
import TheFooter from "./effect/TheFooter.vue";
export default {
  components: {
    "the-header": TheHeader,
    "the-footer": TheFooter
  }
};
</script>
<style lang="scss">
h1,
h2,
h3 {
  font-family: $effect-headline-font;
}

#body {
  @extend %flex-column;
  width: 100vw;
  min-height: 100vh;
  background: $effect-body-bg;
  color: $effect-font-color;
  font-family: $effect-font-family;

  .container,
  .dark-bg,
  .light-bg,
  .second-light-bg {
    width: 100%;
    @extend %flex-column;
  }

  .dark-bg {
    background: $effect-body-bg;
    color: $effect-dark-font-color;
  }

  .light-bg {
    background: $effect-base-color;
    color: $effect-light-font-color;
  }

  .second-light-bg {
    background: $effect-base-color-2;
    color: $effect-light-font-color;
  }
}

.base-btn {
  @include base-btn(red);
  color: $effect-font-color;
}

span.basecolor {
  color: $effect-base-color;
}

@media screen and (max-width: 768px) {
  .container {
    margin-top: 10vh;
  }
}
</style>
