<template>
  <div>
    Coucou, tu veux voir mon nombre:
    <button @click="nimporte.counter = nimporte.counter + 2"> {{ nimporte.counter }} </button>
  </div>
</template>

<script>
import {Store} from '@/Store.js'

export default {
  name: 'coucou',
  data(){
    return {
      nimporte: Store.datas,
    }
  }

}
</script>