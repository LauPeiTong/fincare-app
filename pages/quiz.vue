<template lang="pug">
.fill-height.account-home-page.pa-0.ma-0
    v-row.pa-0.ma-0.upper-row
      upper-title.ma-0(:title="'Quiz'" :icon="'more-vertical'" @goBack="goBackToPreviousPage" :back="true")
    .scroll.scrollbar-hide.ma-0.justify-top.align-center(:style="scrollSize")
      CourseQuiz
</template>

<script>
import { mapGetters } from 'vuex'

import UpperTitle from '../components/UpperTitle.vue'
import CourseQuiz from '../components/course/CourseQuiz.vue'

export default {
  name: 'AccountPage',
  components: {
    UpperTitle,
    CourseQuiz
  },
  layout: 'welcome',
  data () {
    return {
      search: null
    }
  },
  computed: {
    ...mapGetters({
      scrollSize: 'screen/getScrollClass2'
    })
  },
  methods: {
    searchBy (newValue) {
      this.search = newValue
    },
    goBackToPreviousPage () {
      this.$router.go(-1)
    }
  }
}
</script>

<style scoped>
:deep(.scroll) {
  overflow-x: hidden;
  overflow-y: auto;
  width: 100% !important;
}

</style>
