<template>
  <div class='body'>
<home-header></home-header>
<home-content :day='day' :content='content'></home-content>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeHeader from '@/components/Header.vue'
import HomeContent from '@/components/HomeContent.vue'
import axios from 'axios'

export default {
  name: 'home',
  data () {
    return {
      day: '',
      content: []
    }
  },
  components: {
    HomeHeader,
    HomeContent
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('https://api.ooopn.com/history/api.php')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      this.day = res.data.day
      this.content = res.data.content
    }
  }
}
</script>
<style lang="scss" scoped>
.body{
  background: pink;
}
</style>
