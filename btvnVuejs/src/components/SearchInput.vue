<template>
    <div>
        <div id="container_searchInput">
            <slot name="icon" class="icon"></slot>  
            <input v-model="searchInput" @input="searchQuery" type="search" id="searchInput" placeholder="Tìm kiếm sinh viên">
        </div>
        <ul v-if="displayList">
            <li v-for="(person, index) in filteredPeople" :key="index">
                {{ person.name }}
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        props:{
            people:Array,
        },
        data(){
            return {
                searchInput: '',
                filteredPeople: this.people,
                displayList:false
            }
        },
        methods:{
            searchQuery(){
                this.displayList = true;
                this.filteredPeople = this.people.filter((person)=>{
                    return person.name.toLowerCase().includes(this.searchInput.toLowerCase());
                });
            }
        }
    }
</script>
<style scoped>
#container_searchInput{
    display: flex;
    align-items: center;
    position: relative;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 5px;
    width: 250px;

}
#searchInput{
    width: 100%-18px;
    border: none;
    outline: none;
    border-radius: 5px;
}
::v-deep(.icon) {
    position: absolute;
    left: -100px; /* Điều chỉnh icon bên phải input */
    font-size: 18px;
    cursor: pointer;
}
</style>