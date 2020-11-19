<template>
  <div class="home">
    <top-view />
    <map-view />
    <sales-view />
    <bottom-view />
  </div>
</template>

<script>
import TopView from '@/components/TopView'
import MapView from '@/components/MapView'
import SalesView from '@/components/SalesView'
import BottomView from '@/components/BottomView'

export default {
  name: 'Home',
  components: {
    TopView,
    MapView,
    SalesView,
    BottomView
  }
}
</script>

<style>
.home {
  width: 100%;
  height: 100%;
  padding: 20px;
  background: #eee;
  box-shadow: border-box;
}
</style>
