<template>
    <div class="d-flex justify-content-center">
        <div class="mx-5">
            <h3>List Foods</h3>
            <div v-for="(food, index) in foods" :key="index">
                <label :for="index">{{ food.name }}</label>
                <input type="checkbox" name="{{ food.name }}" @click="addFoods(food.name)" :id="index">
            </div>
        </div>
        <div class="d-flex gap-1">
            <button @click="addFull()">&gt;</button>
            <button @click="addFull()">&lt;</button>
        </div>
        <div class="mx-5">
            <h3>Selected Foods:</h3>
            <div v-for="(selectedFood, index) in selectedFoods" :key="index">
                <label :for="'Selectedfood' + index">{{ selectedFood  }}</label>
                <input type="checkbox" :checked="true" :id="'Selectedfood' + index" @click="deleteFood(selectedFood)">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        foods: Array,
    },
    data() {
        return {
            selectedFoods: [],
        }
    },
    methods: {
        addFoods(foodName) {
            if (this.selectedFoods.includes(foodName)) {
                this.selectedFoods = this.selectedFoods.filter((food) => {
                    return food !== foodName;
                })
            } else {
                this.selectedFoods.push(foodName);
            }
        },
        deleteFood(foodName) {
            this.selectedFoods = this.selectedFoods.filter((food) => {
                return food !== foodName;
            })
        },
        addFull() {
            if(this.selectedFoods.length === this.foods.length) {
                this.selectedFoods=[];
            }else{
                this.selectedFoods = this.foods.map(food => food.name);
            }
        }
    }
}
</script>
<style scoped>
input {
    display: none;
}
</style>