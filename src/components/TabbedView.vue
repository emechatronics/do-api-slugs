<template>
  <section class="container">
      <b-tabs v-model="activeTab" size="is-medium" @change="onChange">
          <b-tab-item label="Droplet Sizes">
            <Sizes />
          </b-tab-item>

          <b-tab-item label="Distro Images">
              <DistroImages />
          </b-tab-item>

          <b-tab-item label="App Images">
              <AppImages />
          </b-tab-item>

          <b-tab-item label="Regions">
              <Regions />
          </b-tab-item>

          <b-tab-item label="Kubernetes Versions">
              <Kubernetes />
          </b-tab-item>
      </b-tabs>
  </section>
</template>

<script>
import Sizes from './Sizes.vue'
import DistroImages from './DistroImages.vue'
import AppImages from './AppImages.vue'
import Regions from './Regions.vue'
import Kubernetes from './Kubernetes.vue'

export default {
  data () {
    return {
      activeTab: 0
    }
  },
  components: {
    Sizes,
    DistroImages,
    AppImages,
    Regions,
    Kubernetes
  },
  methods: {
    onChange: function (tab) {
      if (tab === 0) {
        this.$root.$emit('tab', 'sizes')
      } else if (tab === 1) {
        this.$root.$emit('tab', 'distro-images')
      } else if (tab === 2) {
        this.$root.$emit('tab', 'app-images')
      } else if (tab === 3) {
        this.$root.$emit('tab', 'regions')
      } else if (tab === 4) {
        this.$root.$emit('tab', 'k8s')
      }
    }
  }
}
</script>
