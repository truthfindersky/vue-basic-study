<template>
  <div class="container">
    <div class="row">
    <IopSlotBookList />
  </div>
  </div>
</template>

<script>
import IopSlotBookList from './components/IopSlotBookList.vue'

export default {
  name: 'AppIopSlotBook',
  components: {
    IopSlotBookList,
  }
}
</script>

<style>
#AppIopSlotBook {
  margin-top: 30px;
  margin-bottom: 30px;
  text-align: center;
}
</style>


































<!-- <template>
<h2>Vue Slots</h2>
<div class="container">
<div class="row">
<IopSlot contentName="Moana" contentTitle="Architect & Engineer" />
<IopSlot contentName="Mamun" contentTitle="Web designer" />
</div>
</div>
</template>

<script>
import IopSlot from './components/IopSlot.vue'

export default {
  name: 'AppIopSlot',
  data() {
    return {
    }
  },
  components: {
    IopSlot
  }
}
</script>

 -->
