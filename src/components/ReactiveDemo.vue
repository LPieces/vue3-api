<template>
    <div>
        <h1>foo:{{ foo }}</h1>
    </div>
</template>

<script>
import { reactive,ref, toRef, toRefs } from 'vue'
export default {
    name: 'ReactDemo',
    setup(props, ctx){
        const proxyObj = reactive({
            a: 1,
            b: 2,
            c: {
                a: 1,
                b: 2
            }
        })
        const count = ref({
            a:1,
            b:2
        })
        console.log(count.a) // undefined
        console.log(count.value.a) // 1
        console.log(proxyObj);

        const state = reactive({
        foo: 1,
        bar: 2
        })
        
        const fooRef = toRef(state, 'foo')

        fooRef.value++
        console.log(state.foo) // 2

        state.foo++
        console.log(fooRef.value) // 3
        
        const stateAsRefs = toRefs(state);
        console.log(stateAsRefs);  // 普通对象
        return{
            ...stateAsRefs
        }
    }
}
</script>