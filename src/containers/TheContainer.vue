<template>
  <div class="c-app">
    <TheSidebar/>
    <CWrapper>
      <TheHeader/>
      <div class="c-body">
        <main class="c-main">
                            <Timer class="timer-component" />

          <CContainer fluid>
            <transition name="fade">
              <router-view></router-view>
            </transition>
          </CContainer>
          
        </main>
        <TheFooter/>
      </div>
    </CWrapper>
  </div>
</template>

<script>
import TheSidebar from './TheSidebar'
import TheHeader from './TheHeader'
import TheFooter from './TheFooter'

import Timer from "@/components/Timer"

export default {
  name: 'TheContainer',
  components: {
    TheSidebar,
    TheHeader,
    TheFooter,
    Timer,
  }
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.timer-component {
  width: 80%;
  max-width: 500px;
  margin: 30px auto;
}

</style>
