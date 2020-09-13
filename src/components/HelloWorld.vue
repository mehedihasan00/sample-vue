<template>
  <h1>{{ msg }}</h1>
  <button @click="inc">count is: {{ count }}</button>
  <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
</template>

<script>
import { ref } from 'vue'
export default {
  props: {
    msg: String
  },
  setup (props) {
    console.log(props.msg)
    const count = ref(0)
    const inc = () => {
      count.value++
    }
    return {
      count,
      inc
    }
  }
}
</script>
