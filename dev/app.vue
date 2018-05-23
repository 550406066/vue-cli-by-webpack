<template>
    <div id="app">
        <span>{{msg}}</span>
        <p class="test">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptate nostrum accusantium labore quos distinctio molestiae, est asperiores sint porro pariatur nam. Id eos totam assumenda quidem, vel maxime non expedita.</p>
    </div>
</template>
<script>
import Vue from 'vue'
    export default {
        name:'app',
        data(){
            return {
                msg:"hello vue !!"
            }
        },
    }
</script>
<style >
    .test{
        columns: #030303;
    }
</style>

