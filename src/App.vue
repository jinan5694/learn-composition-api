<template>
  <div>
    <button @click="increment">
      Count is: {{ state.count }}, double is: {{ state.double }}
    </button>
    <div>{{x}}</div>
    <div>{{y}}</div>
  </div>
</template>
<script>
import { reactive, computed } from '@vue/composition-api'
import { useMousePosition } from './components/position'

export default {
  setup () {
    const { x, y } = useMousePosition()
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2)
    })

    function increment () {
      state.count++
    }

    return {
      state,
      increment,
      x,
      y
    }
  }
}
</script>
