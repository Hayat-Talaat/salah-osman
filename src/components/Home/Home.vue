<template>
  <transition
    name="router-anim"
    enter-active-class="animated fadeInUpBig"
    leave-active-class="animated fadeInUpBig"
  >
    <div>
      <app-header></app-header>

      <app-home-services></app-home-services>
      <app-home-productes></app-home-productes>
      <app-home-features></app-home-features>
    </div>
  </transition>
</template>
<script>
import Header from "../shared/header.vue";
import homeServices from "./children/homeServices.vue";
import homeProductes from "./children/homeProductes.vue";
import homeFeatures from "./children/homeFeatures.vue";
export default {
  components: {
    appHeader: Header,
    appHomeServices: homeServices,
    appHomeProductes: homeProductes,
    appHomeFeatures: homeFeatures
  }
};
</script>

<style>

@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";

.router-anim-enter-active {
  animation: coming 1s;
  animation-delay: 0.5s;
  opacity: 0;
}
.router-anim-leave-active {
  animation: going 1s;
}

@keyframes going {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50px);
    opacity: 0;
  }
}
@keyframes coming {
  from {
    transform: translateX(-50px);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}
</style>
