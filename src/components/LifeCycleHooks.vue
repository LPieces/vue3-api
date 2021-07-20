<template>
    
</template>

<script>
import { getCurrentInstance, onBeforeMount, onMounted, onUpdated, watchEffect } from 'vue'
export default {
    name: 'LifeCycleHooks',
    setup(porps, ctx){
        const instance = getCurrentInstance();
        console.log(instance); // 获取当前组件的实例
        onMounted(()=>{
            console.log('onMounted')
        })
        onBeforeMount(()=>{
            console.log('onBeforeMount')
        })
        onUpdated(()=>{
            console.log("onUpdated");
        })
        watchEffect(()=>{
            console.log('watchEffect');
        })
    }
}
</script>