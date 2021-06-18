<template>
  <div>
    <h1>{{ count }}</h1>
    <h2>{{ state.num }}</h2>
    <h3>{{ num2 }}</h3>
    <!-- <Test :title="title" :count="count2" @addCount="addCount" />
    <ReactiveDemo />
    <ComputedDemo />
    <readonlyDemo />
    <watchEffectDemo /> -->
    <watchDemo />
  </div>
</template>

<script>
import { reactive, ref, toRefs } from 'vue'
import Test from './components/Test.vue'
import ReactiveDemo from './components/ReactiveDemo.vue'
import ComputedDemo from './components/ComputedDemo.vue'
import readonlyDemo from './components/readonlyDemo.vue'
import watchEffectDemo from './components/watchEffectDemo.vue'
import watchDemo from './components/watchDemo.vue'
export default {
  name: 'App',
  components:{
    Test,
    ReactiveDemo,
    ComputedDemo,
    readonlyDemo,
    watchEffectDemo,
    watchDemo
  },
  setup(props, context){
    const { attrs, emit, slots } = context;
    console.log(context)
    const title = ref("我是title");
    const state = reactive({
      num: 1
    })
    const count = ref(0);
    const state2 = reactive({
      num2: 2
    });
    setTimeout(()=>{
      title.value = "我是Vue3.0";
    },3000);
    const count2 = ref(2);
    const addCount = (num) => {
      count2.value += num;
    }
    return{
      count,
      state,
      ...toRefs(state2),
      title,
      count2,
      addCount
    }
  }
}
</script>

