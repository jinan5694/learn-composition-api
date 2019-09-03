<template>
  <div>{{foo}}{{test}}</div>
</template>

<script>
import { createComponent } from '@vue/composition-api'

export default {
  props: {
    foo: String
  },
  setup (props) {
    const test = 'hello'
    return () => <div>{props.foo}</div>
  }
}
</script>


