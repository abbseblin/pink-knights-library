<template>
    <div>
        <div class="cart">
            <div class="bg-gray-500 p-2 rounded-lg ">
                <button @click="toggle" class="bg-gray-600 rounded-full w-10 h-10 pl-auto">🛒</button>
                <div v-if="open">Text!</div>
            </div>
        </div>
    </div>
</template>

<style>
.cart{  
    bottom:0;
    right: 0;
    position: absolute;
    margin-bottom:-100vh;
    padding: 10px;
}
</style>
<script>
export default {
    data() {
    return{
    open: true
    }
    },
    methods: {
        toggle(){
            this.open = !this.open;
            console.log(this.open)
        }
    }
}
</script>
