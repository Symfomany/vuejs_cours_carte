<template>
  <div>
    Message: {{ msg }} Nb: {{ nimporte.counter }}
    <a @click="nimporte.counter += 5">Up!!!!</a>
  </div>
</template>

<script>
import {Bus} from '@/Bus.js'
import {Store} from '@/Store.js'

export default {
  name: 'navbar',
  created() {
    Bus.$on('faim', () =>
        this.msg = "J'ai faim!"
    );
  },
  data(){
    return {
      msg: '',
      nimporte: Store.datas
    }
  },
}
</script>