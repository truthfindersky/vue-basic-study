<template>

  <h1>Dynamic Components</h1>

  <Button @click="activeTab = 'TabA'">Tab A</Button>
  <Button @click="activeTab = 'TabB'">Tab B</Button>
  <Button @click="activeTab = 'TabC'">Tab C</Button>

  <!-- <TabA v-if="activeTab === 'TabA'" />
  <TabB v-if="activeTab === 'TabB'" />
  <TabC v-if="activeTab === 'TabC'" /> -->

  <!-- it help preventing data loss during tab switching -->
  <keep-alive>
  <component :is="activeTab"/>
  </keep-alive>

</template>

<script>
import TabA from './components/JopTabA.vue'
import TabB from './components/JopTabB.vue'
import TabC from './components/JopTabC.vue'

export default {
  name: 'AppJopTab',
  data() {
    return {
      activeTab: 'TabA'
    }
  },
  components: {
    TabA,
    TabB,
    TabC,
}
}
</script>

<style>
#AppJopTab{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
