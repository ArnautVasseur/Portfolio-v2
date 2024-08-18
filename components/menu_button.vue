<template>
  <div class="box" :class="background">
      <div class="box__left">
        <h2>{{title}}</h2>
        <h3>{{subtitle}}</h3>
      </div>
      <icon-project class="icon-1" v-if="icon == 'projects'"/>
      <icon-skill class="icon-2" v-else-if="icon == 'skill'"/>
      <icon-contact class="icon-3" v-else-if="icon == 'contact'"/>
  </div>
</template>

<script lang="ts" setup>
const background = computed(() =>({
  "background-100": props.icon === "projects",
  "background-200": props.icon === "skill",
  "background-300": props.icon === "contact"
}))

// @ts-ignore
const props = defineProps({
  title: String,
  subtitle: String,
  icon: String
})

</script>

<style scoped lang="scss">

.box{
  width: 550px;
  height: 175px;
  padding: 35px;
  position: relative;
  background: $dark-bg-100;
  text-align: center;
  display: flex;
  justify-content: space-between;
  align-items: center;
  overflow: hidden;
  z-index: 1;
  box-shadow: 0px 0px 70px $dark-bg-500;
  transition: 300ms;

  &.background-100{
    box-shadow: 0px 0px 70px darken($primary-500, 10%);
    &::before{
      background: darken($primary-500, 10%);
    }
    &:hover{
      box-shadow: 0px 0px 200px darken($primary-500, 0%)
    }
  }

  &.background-200{
    box-shadow: 0px 0px 70px darken($primary-300, 10%);
    &::before{
      background: darken($primary-300, 10%);
    }
    &:hover{
      box-shadow: 0px 0px 200px darken($primary-300, 0%)
    }
  }

  &.background-300{
    box-shadow: 0px 0px 70px darken($primary-100, 10%);
    &::before{
      background: darken($primary-100, 10%);
    }
    &:hover{
      box-shadow: 0px 0px 200px darken($primary-100, 0%)
    }
  }

  &__left{
    text-align: right;
    
    h2, h3{
      color: white;
      transition: 300ms;
    }

    h2{
      font-size: 2.5em;
      margin-bottom: 20px;
    }

    h3{
      font-size: 1.5em;
    }
  }
}

.box::before{
  content: '';
  width: 500px;
  height: 200px;
  position: absolute;
  z-index: -1;
  transform: skew(-35deg) translate(330px);
  transition: 400ms;
}

.box:hover::before{
  transform: skew(-35deg) translate(-170px);
}

.box:hover{
  
  h2, h3{
    text-shadow:
    0 0 7px #fff,
    0 0 10px #fff,
    0 0 21px #fff,
    0 0 42px $primary-100,
    0 0 82px $primary-100,
  }

  .icon-1, .icon-2,.icon-3{
    filter: drop-shadow(0px 0px 30px lighten($primary-100, 55%) );
  }
}

.icon-1, .icon-2, .icon-3{
  transition: 300ms;
}
</style>