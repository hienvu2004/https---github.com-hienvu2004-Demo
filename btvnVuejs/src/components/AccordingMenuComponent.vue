<template>
    <ul>
       <li v-for="(song, index) in songs" :key="index">
            <label :for="'checkbox-' + index" @click="toggleSong(index)" >{{ song.name }}</label>
            <input type="checkbox" :id="'checkbox-' + index">
            <div v-if="selectedIndex ==index">
                {{ song.content }}
            </div>   
       </li>
    </ul>
</template>

<script>
export default {
    props: {
        songs: Array
    },
    data() {
        return {
            selectedIndex: null,
        };
    },
    methods: {
        toggleSong(index){
           if( this.selectedIndex == null){
             this.selectedIndex = index;
           }else{
             this.selectedIndex = null;
           }
        }
    }
};
</script>

<style scoped>
input {
    display: none;
}
li {
    list-style: none;
}
</style>
