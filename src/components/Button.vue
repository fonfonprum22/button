<template>
    <div>
        <button 
            class="btn btn-outline-primary" 
            v-on:click = "counter()"
        >{{label}}</button>

        <lottie-animation
            path="../res/like.json"
        />

    </div>
</template>

<script>
// import LottieAnimation from 'lottie-vuejs'

export default {
    components: {
        // LottieAnimation
    },
    props: {
        label:String
    },
    methods: {
        counter() {
            this.$emit("onCounter", this.label)
        }
    }
    
}
</script>

<style>
.btn {
    height: 50px;
    width: 50px;
    border-radius: 50%;
    border: 1px solid black;
}
</style>