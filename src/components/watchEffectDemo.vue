<template>
    
</template>

<script>
import { ref, watchEffect } from 'vue'
export default {
    name: 'watchEffectDemo',
    setup(){
        // const count = ref(0);
        // setTimeout(()=>{
        //     count.value = 1;
        // },1000);
        // setTimeout(()=>{
        //     count.value = 2;
        // },3000);
        // const stop = watchEffect(()=>{
        //     console.log(count.value);
        // })
        // setTimeout(()=>{
        //     stop()
        // },2000);
        const count = ref(0);
        function getData(){
            return new Promise((resolve)=>{
                resolve(100)
            })
        }
        setTimeout(()=>{
            count.value = 2;
        },1000);
        const stop = watchEffect(async (onInvalidate)=>{
            console.log(count.value);
            const data = await getData();
            console.log(data);

            onInvalidate(()=>{
                console.log("onInvalidate is triggered")
            });
        });
    }
}
</script>