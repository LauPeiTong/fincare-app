<template lang="pug">
  v-row.bottom-nav.bottom-column-content-area.pa-4(no-gutters)
    v-col.flex.bottom-nav--col.px-0.mx-0
      f-button.bottom-nav--button(
        :label="isEnrolled ? 'Continue' : 'Enroll Now'"
        block
        dark
        :color="$vuetify.theme.themes.light.primary"
        @click=""
      )
</template>

<script>
import { mapGetters, mapActions } from 'vuex'
import FButton from './fincare-components/FButton.vue'

export default {
  name: 'BottomNav',
  components: { FButton },
  data () {
    return {
    }
  },
  computed: {
    ...mapGetters({
      isEnrolled: 'course/isEnrolled'
    })
  },
  methods: {
    ...mapActions({
    })
  }
}
</script>

<style lang="scss" scoped>
.bottom-nav {
  position: absolute;
  bottom: 0;
  width: 100%;
  z-index: 100;
}

.bottom-column-content-area {
  border-width: 1px 0 0 0;
  border-color: rgba(193, 193, 193, 0.25);
  border-style: solid;
  background-color: white;
}

</style>
