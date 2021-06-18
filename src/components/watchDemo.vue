<template>
    
</template>
<script>
import { reactive, ref, watch } from 'vue';
export default {
    name: 'watchDemo',
    setup(){
        const count = ref(0);
        const name = ref(0);
        const state = reactive({
            a: 0
        })
        setTimeout(()=>{
            count.value = 2;
            name.value = 2;
            state.a = 2;
        },2000)
        watch(()=>[count.value,name.value], ([newCount,oldCount],[newName,oldName])=>{
            console.log(newCount,oldCount,newName,oldName)
        })
        watch(()=>state.a,(newA,oldA)=>{
            console.log(newA,oldA)
        })
    }
}
</script>