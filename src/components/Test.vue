<template>
    <div>
        <h1>{{ title }}</h1>
        <h2>{{ count }}</h2>
        <button @click="addCount">addCount</button>
    </div>
</template>

<script>
import { watchEffect, watch } from 'vue'
export default {
    name: 'Test',
    props:{
        title: String,
        count: Number
    },
    emits: ['addCount'],
    setup(props, ctx){
        console.log(props)
        watchEffect(()=>{
            console.log("watchEffect",props.title)
        })
        watch(()=>{
            return props.title;
        },(newValue)=>{
            console.log("watch",newValue);
        })
        const addCount = () =>{
            ctx.emit("addCount",1);
        }
        return{
            addCount
        }
    }
}
</script>
