<template>
  <span v-el:trigger>
    <slot>
    </slot>
  </span>
  <div class="popover"
    v-bind:class="{
    'top':placement === 'top',
    'left':placement === 'left',
    'right':placement === 'right',
    'bottom':placement === 'bottom'
    }"
    v-el:popover
    v-show="show"
    :transition="effect">
      <div class="arrow"></div>
      <h3 class="popover-title" v-show="title">{{title}}</h3>
      <div class="popover-content">
        {{{content}}}
      </div>
  </div>
</template>

<script>
import PopoverMixin from './popoverMixins.js'
  export default {
    mixins: [PopoverMixin]
  }
</script>
<style>
.scale-transition,
.fade-transition {
  display: block;
}
.scale-enter {
  animation:scale-in 0.15s ease-in;
}
.scale-leave {
  animation:scale-out 0.15s ease-out;
}
@keyframes scale-in {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}
@keyframes scale-out {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  100% {
    transform: scale(0);
    opacity: 0;
  }
}


</style>
