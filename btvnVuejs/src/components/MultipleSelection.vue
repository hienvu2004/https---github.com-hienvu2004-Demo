<template>
    <div>
        <select v-model="selectedFood" class="form-select w-25">
            <option @click="addChoice(food.name)" v-for="food in foods" :key="food.id" :value="food.id">
                {{ food.name }}
            </option>
        </select>
    </div>
</template>
<script>
    export default {
        props:{
            foods:Array
        },
        data() {
            return {
                // Define your data here
                selectedFood:[],
            };
        },
        methods: {
            addChoice(foodName){
                this.selectedFood.push(foodName);   
            }
        }
    };

</script>
<style>
</style>