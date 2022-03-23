<template>
<div class="q-pa-md">
  <q-header elevated>
    <q-toolbar>
      <q-btn
        flat
        dense
        round
        icon="menu"
        aria-label="Menu"
        @click="changeTitle"
      />
        <!-- @click="leftDrawerOpen = !leftDrawerOpen" -->

      <q-toolbar-title>
        {{ title }}
      </q-toolbar-title>

      <!-- <div>Quasar v{{ $q.version }}</div> -->
    </q-toolbar>
  </q-header>
</div>
</template>

<script>

export default{
  name: 'Header',
  data() {
    return {

    }
  },

  props: {
    title: {
      type: String,
      default: 'SCU App Update'
    }
  },

  methods: {
    changeTitle(e) {
      console.log(e);
      this.$emit('changeTitle', 'Component update')
    }
  }

}
</script>

<style scoped>

</style>