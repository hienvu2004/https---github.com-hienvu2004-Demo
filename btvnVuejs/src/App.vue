<template>
  <div>
    <SearchInput :people="people">
      <template #icon>
          <span class="search-icon">🔍</span>
      </template>
    </SearchInput>
    <CheckboxComponent></CheckboxComponent>
    <AccordingMenuComponent :songs="songs"></AccordingMenuComponent>
    <SelectBothSides :foods="foods"></SelectBothSides>
    <MultipleSelection :foods="foods"></MultipleSelection>
  </div>
</template>
<style>
</style>
<script>
import SearchInput from './components/SearchInput.vue';
import CheckboxComponent from './components/CheckboxComponent.vue';
import AccordingMenuComponent from './components/AccordingMenuComponent.vue';
import SelectBothSides from './components/SelectBothSides.vue';
import MultipleSelection from './components/MultipleSelection.vue';
  export default{
    components:{
      SearchInput,
      CheckboxComponent,
      AccordingMenuComponent,
      SelectBothSides,
      MultipleSelection,
    },
    data() {
      return {
        people:[
          {name: "John", age:"21"},
          {name: "Jane", age:"23"},
          {name: "Mike", age:"25"}
        ],
        songs:[
          {name:"Snow",content:"Snow is ..."},
          {name:"Rain",content:"Rain is ..."},
          {name:"Sun",content:"Sun is ..."},
          {name:"Moon",content:"Moon is ..."},
        ],
        foods:[
          {name:"Apple", color:"Red"},
          {name:"Banana", color:"Yellow"},
          {name:"Orange", color:"Orange"},
          {name:"Grape", color:"Purple"},
          {name:"Mango", color:"Yellow"},
        ],
      }
    },
    methods: {
      // Define your methods here
    }
  }
</script>