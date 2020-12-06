<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

      </q-toolbar>
      <div class="q-px-lg q-pt-xl q-mb-md">
        <div class="text-h3">ToDo</div>
        <div class="subtittle1">{{ todayDate }}</div>
      </div>
      <q-img 
      src="~assets/mountains.jpg"
        class="header-image absolute-top"></q-img>
      
    </q-header>

      <q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        :width="250"
        :breakpoint="600"
      >
        <q-scroll-area style="height: calc(100% - 185px); margin-top: 185px; border-right: 1px solid #ddd">
          <q-list padding>
            <q-item to="/" exact clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="list" />
              </q-item-section>

              <q-item-section>
                ToDo
              </q-item-section>
            </q-item>

            <q-item to="/help" exact clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="help" />
              </q-item-section>

              <q-item-section>
                Help
              </q-item-section>
            </q-item>

          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="~assets/mountains.jpg" style="height: 185px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="https://lh3.googleusercontent.com/-ecmU93vNx6M/UCxM_HbRDiI/AAAAAAAABd0/zO2tGfFFAwALRdyNjpGbH5CfgSE6JO76ACEwYBhgLKtMDAL1OcqwPHyWKp6ZT-IDDv0nO0Tu2LXOMYWYjQp5v44tAXl-0f6hctaTUjETjBZM6gjqzjWpgPlFzl4AgbClMDf4fRWoBwEGIsZVyw-CvScok9F1g5oTvlI0Y_yYYalEhmY8rlS_QsBCB6lGFaY_ZRxDmwPC4d9Zb50TXoVMsbeQBlWVp0IDSihew0dBRgVbVXBdyyMEPCuTPSdVTEem0o0IvAJ1yjm9rjENwF7fQwBIvTC7h8qTTYjdP1h5jCY7Ob1oy8sw-lyk8ywkFCxS-_gyoHyPQmekRXibP-PV3yLvme0A0uKekRhv7uzIJIUyDdWkR0JDaVk7FdPV-849Xo3T3cicQinhVR52Aa0qpuE2JcKdN99syvmArvXM3BObNyNyGziq-79zCqv-EC8BguGb7Y_petfUuEx0gVTQN5ROajXL72xtcfDkfOZw8zobcFE4IolkCfRhhr_Ko_pb1IgcNmxHNrbQwRr9B5N8urCpWpjh4XezbqNyOMLunbq4UP-GLR_u5tDhPzsBKOMYrbV-voTbRqWhh5TrhsSUBfSYo8C3chc2ELSDmd83OKOpuJ9p5ZFCc_PDpBQssdB8GsA6rmIB0NnJJe1EpBQrkO-xyw6Uw_YOx_gU/w139-h140-p/pom.JPG">
            </q-avatar>
            <div class="text-weight-bold">Andi Dermawan</div>
            <!-- <div>@rstoenescu</div> -->
          </div>
        </q-img>
      </q-drawer>

    <q-page-container>
      <keep-alive>
        <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'
import { date } from 'quasar'



export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      // essentialLinks: linksData
    }
  },
  computed:{
    todayDate(){
      let timeStamp = Date.now()
      return date.formatDate(timeStamp, 'dddd D MMMM')
    }
  }
}
</script>
<style lang="scss">
.header-image{
  height: 100%;
  // width: 100%;
  z-index: -1;
  opacity: 0.2;
  filter: grayscale(100%);
}

</style>
