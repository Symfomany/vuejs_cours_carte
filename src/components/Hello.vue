<template>
  <div class="hello">
    <h2>Essential Links</h2>
    <rightmenu :nb="nimporte.counter" :pizzas="nbPizza"></rightmenu>
    <button @click="nimporte.counter = nimporte.counter + 1">up!</button>
    <button @click="nbPizza = nbPizza - 1">eat!</button>
  </div>
</template>

<script>
import RightMenu from '@/components/RightMenu'
import {Bus} from '@/Bus.js'
import {Store} from '@/Store.js'

export default {
  name: 'hello',
  data(){
    return {
      nimporte: Store.datas,
      nbPizza: 10
    }
  },
  components: {rightmenu: RightMenu},
  watch: {
    nbPizza: function(){
      if(this.nbPizza <= 3 ){
        Bus.$emit('faim');
      }
    }
  }
}
</script>