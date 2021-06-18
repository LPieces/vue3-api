<template>
    
</template>

<script>
import { ref, computed } from 'vue'
export default {
    name: 'ComputedDemo',
    setup(props, ctx){
        const lpieces = ref('lpieces');
        const strLpieces = computed(()=>{
            return 'Ljh_'+lpieces.value
        })
        const str2 = computed({
            get(){
                return 'LJH'+ lpieces.value
            },
            set(val){
                lpieces.value = val;
                console.log("str2被修改了")
            }
        })
        console.log(strLpieces.value)
        console.log(str2.value)
        str2.value = 'LPIECES';
        console.log("set lpieces",lpieces.value)
    }
}
</script>