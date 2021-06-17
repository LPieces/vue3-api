<template>
  <div>
    <!-- <h1>{{ count }}</h1> -->
    <h2>{{ num }}</h2>
  </div>
</template>

<script>
import { reactive, ref, toRefs, h } from 'vue'
export default {
  name: 'App',
  setup(props, context){  // props
  console.log(props);
    const state = reactive({
      count: 0
    })
    const num = ref(0);
    console.log(num); // value取值

    // return{
    //   ...toRefs(state),
    //   num
    // }
    return () => h('h1',[num.value])
  }
}
</script>

