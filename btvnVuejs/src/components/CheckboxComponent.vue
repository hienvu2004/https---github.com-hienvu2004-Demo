<template>
    <div>
        <input type="checkbox" @click="!show" v-model="show" name="" id="">
        <div v-show="show == true">
            Day la noi dung cua tab 1
        </div>
    </div>
</template>
<script>
    export default{
        data() {
            return {
                show:false,
            }
        }
    }
</script>