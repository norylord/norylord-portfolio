<template>
  <div ref="container" class="keen-slider" style="height: 100%">
    <div class="keen-slider__slide number-slide1" :class="{'slide-active': current === 1}">1</div>
    <div class="keen-slider__slide number-slide2" :class="{'slide-active': current === 2}">2</div>
    <div class="keen-slider__slide number-slide3" :class="{'slide-active': current === 3}">3</div>
    <div class="keen-slider__slide number-slide4" :class="{'slide-active': current === 4}">4</div>
    <div class="keen-slider__slide number-slide5" :class="{'slide-active': current === 5}">5</div>
    <div class="keen-slider__slide number-slide6" :class="{'slide-active': current === 6}">6</div>
  </div>
</template>

<script setup>
import { useKeenSlider } from "keen-slider/vue.es";
import "keen-slider/keen-slider.min.css";
import {ref} from "vue";

const current = ref(1);
const [container] = useKeenSlider(
    {
      loop: true,
      slides: {
        origin: "center",
        perView: 3,
        spacing: 24,
      },
      vertical: true,
      slideChanged: (s) => {
        current.value = s.track.details.rel + 1;
      },
    },
    [
      (slider) => {
        let timeout;
        let mouseOver = false;
        function clearNextTimeout() {
          clearTimeout(timeout);
        }
        function nextTimeout() {
          clearTimeout(timeout);
          if (mouseOver) return;
          timeout = setTimeout(() => {
            slider.next();
          }, 5000);
        }
        slider.on("created", () => {
          slider.container.addEventListener("mouseover", () => {
            mouseOver = true;
            clearNextTimeout();
          });
          slider.container.addEventListener("mouseout", () => {
            mouseOver = false;
            nextTimeout();
          });
          nextTimeout();
        });
        slider.on("dragStarted", clearNextTimeout);
        slider.on("animationEnded", nextTimeout);
        slider.on("updated", nextTimeout);
      },
    ]
);
</script>

<style>
.keen-slider {
  z-index: 1;
}
[class^="number-slide"],
[class*=" number-slide"] {
  background: #011221;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 50px;
  color: #fff;
  font-weight: 500;
  height: 300px;
  max-height: 100vh;
  border-radius: 16px;
  opacity: .5;
  transition: opacity .2s ease-in-out;
  filter: blur(6px);
}

.slide-active {
  opacity: 1;
  filter: none
}
</style>
