<template>
    <div>
        <div class='time'>今天是<div>{{day}}</div></div>
        <ul class='content'>
            <li v-for="item in content" :key='item'>
                {{item}}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeContent',
  props: {
    day: String,
    content: Array
  }
}
</script>

<style lang="scss" scoped>
    .time{
        display:flex;
        background: pink;
        justify-content: center;
    }
    .content{
        background: pink;
        justify-content: center;
    }

</style>
