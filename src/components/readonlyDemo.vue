<template>
    
</template>

<script>
import { readonly, reactive } from 'vue'
export default {
    name: 'readonlyDemo',
    setup(){
        const obj = reactive({
            a: 1,
            b: 2,
            c: {
                a: 1
            }
        })
        const obj2 = readonly(obj);
        obj2.a = 2;
        console.log(obj2.a)
    }
}
</script>