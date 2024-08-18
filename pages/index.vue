<script setup lang="ts">
// @ts-ignore
import { useMouse } from '@vueuse/core'

const { x, y } = useMouse()

</script>

<template>
  <div class="container">

    <div class="container__content">
      <div class="container__content__left"></div>

      <div class="container__content__right">

        <menu_button title="Projects" subtitle="Discover my projects" icon="projects"/>
        <menu_button title="Skills" subtitle="My detailed skillset" icon="skill"/>
        <menu_button title="Contact" subtitle="Get in touch with me" icon="contact"/>

      </div>
    </div>
    
    <!-- <div class="container__header">
      
    </div> -->

    

    <div class="custom-cursor"
    :style="{
      left:`${x}px`,
      top:`${y}px`,
      width:`200px`,
      height:`200px`,
    }"
    />
  </div>
</template>

<style scoped lang="scss">

.container{
  width: 100%;

  &__header{
    background: $dark-bg-100;
    // border: $primary-300 1px solid;
    width: 100%;
    height: 100vh;
    overflow: none;

    &__title{
      font-size: 2.5rem;
    }
  }

  &__content{
    // background: $primary-200;
    display: flex;
    width: 100%;
    height: 100vh;

    &__left{
      width: 50%;
      // background: rgba(0, 0, 255, 0.075);
      padding: 100px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &__right{
      width: 50%;
      // background: rgba(255, 0, 0, 0.211);
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      align-items: center;
    }
  }
}

// .custom-cursor{
//   position: absolute;
//   background: $primary-300;
//   border-radius: 100%;
//   transform: translateX(-50%) translateY(-50%);
//   pointer-events: none;
//   overflow: hidden;
//   filter: blur(64px);
// }

.background{
    opacity: 15%;
    width: 100%;
    user-select: none;
    z-index: -1;
    position: absolute;
}

</style>

<script>
  
</script>