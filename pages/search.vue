<template>
  <div class="page">
    search
    <ul>
      <li v-for="(item, index) in list" :key="index">{{item}}</li>
    </ul>
  </div>
</template>

<script type="text/ecmascript-6">
import axios from 'axios'
export default {
  layout: 'search',
  data() {
    return {
      list: []
    }
  },
  async asyncData() {
    let {status, data: { list }} = await axios.get('http://localhost:3000/city/list')
    if (status === 200) {
      return {
        list
      }
    }
  },
  // async mounted() {
  //   let {status, data: { list }} = await axios.get('/city/list')
  //   if (status === 200) {
  //     this.list = list
  //   }
  // },
  components: {
  }
}
</script>
